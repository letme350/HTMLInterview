一、

script start
async1 start
async2
promise1
script end
async1 end
promise2
setTimeout

二、

```js
function formatArr(data) {
  return data.reduce((arr, item) => {
    arr.push(item)
    if (item.children) {
      arr.push.apply(arr, formatArr(item.children))
      delete item.children
    }
    return arr
  }, [])
}

console.log(formatArr(data))
```

三、

```js
const debounce = (func, wait = 50) => {
  let timer = 0
  return function (...args) {
    if (timer) clearTimeout(timer)
    timer = setTimeout(() => {
      func.apply(this, args)
    }, wait)
  }
}
```



