# node-party

node 地下铁官网

## 提取网页中的文字并去重
提取所使用的文字，然后使用 iconfont webfont 功能生成字体，选择字体：阿里巴巴普惠体-Light

```js
const text = document.body.innerText;
const result = {};
text.split('').forEach((t) => {
    console.log(t, t.charCodeAt(0));
    const charCode = t.charCodeAt(0);
    if (charCode !== 10 && charCode !== 32 && (charCode < 58880 || charCode > 58883)) {
        if(result[t]) {
            result[t] += 1;
        } else {
            result[t] = 1;
        }
    }
});
console.log(Object.keys(result).join(''));
```

## 地址坐标提取
https://lbs.amap.com/console/show/picker