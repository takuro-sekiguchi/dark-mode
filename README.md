# ダークモード切り替え可能なサイト

[デモサイトはこちら](https://taku-web3.com/project/dark-mode/index.html)

## ■新しく学んだこと
- document.onclickの使い方
- overflow: hidden;で画面の揺れを防げる



```css
main {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: -1;
}
```
position: absolute;を使ってheight: 100vh;を指定すると、画面全体に適用されてしまう。
そのため、z-indexを使ってレイヤーを下に下げないと他の要素が全て隠れてしまう。


```js
icon.onclick = () => {
  document.body.classList.toggle('darkmode')
  if(document.body.classList.contains('darkmode')){
    icon.src = './images/sun.png';
  } else {
    icon.src = './images/moon.png';
  }
};
```
```js
icon.addEventListener('click', () => {
  document.body.classList.toggle('darkmode');
  if(document.body.classList.contains('darkmode')){
    icon.src = './images/sun.png';
  } else {
    icon.src = './images/moon.png';
  }
});
```
どちらも同じ意味になる。
onclickは = () => {}で書く

.contains('要素名')で、要素が含まれているかを判別できる。
JavaScriptからも画像(src属性)の操作ができる。