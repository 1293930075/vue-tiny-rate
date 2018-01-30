# Vue Tiny Rate


> 最小的Vue评级组件



## 功能

* 基于☆ 和 ★
* 支持小数评级
* 主题颜色配置
* 动画效果
* 星星大小

## 安装和使用

先从npm安装到项目里

```bash
npm install vue-tiny-rate --save
```

在项目里导入Rate组件

```javascript
import Rate from 'vue-tiny-rate';

new Vue({
    components: {
        Rate
    }
})
```

HTML里使用

```html
<Rate />
```
![](./img/00.png)


## 配置项

- `value {number|string}` : 评几星，支持小数 `默认:0`

```html
<Rate value="0.5"></Rate>
<Rate value="1"></Rate>
<Rate value="3.6"></Rate>
```
![](./img/01.png)



- `readonly {boolean}` : 是否是只读. `default:false`

```html
<Rate value="0.5"></Rate>
<Rate value="1"></Rate>
<Rate value="3.6" readonly="true"></Rate>
```
![](./img/01.gif)

- `length {number|string}` : 一共几个星 `默认:5`

```html
<Rate value="2" length="4"></Rate>
<Rate value="3.6" length="8"></Rate>
<Rate value="7.6" length="10"></Rate>
```
![](./img/02.png)


- `theme {color|enum('yellow','green','blue','red','purple','orange','black','wihte')}`: 主题色. `默认: yellow`

```html
<Rate value="4.5">Yellow</Rate>
<Rate value="4.5" theme="green">Green</Rate>
<Rate value="4.5" theme="blue">Blue</Rate>
<Rate value="4.5" theme="red">Red</Rate>
<Rate value="4.5" theme="purple">Purple</Rate>
<Rate value="4.5" theme="orange">Orange</Rate>
<Rate value="4.5" theme="black">Black</Rate>
<Rate value="4.5" theme="#91d5ff">#91d5ff</Rate>

```

![](./img/03.png)


- `size {number|string}`: 星星的大小. 

```html
<Rate value="4.5" size='12px'>12px</Rate>
<Rate value="4.5" size='16px'>16px</Rate>
<Rate value="4.5" size='20px'>20px</Rate>
<Rate value="4.5" size='40px'>40px</Rate>
```

![](./img/04.png)


- `animate {number|string}`: 是否有动画. `default:0`

```html
<Rate value="3.5" animate='1'>1s</Rate>
<Rate value="3.5" animate='2'>2s</Rate>
<Rate value="3.5" animate='3'>3s</Rate>
```
![](./img/05.gif)

## Events

- `onRate`: 选中星级后的评价. 

```html
<Rate @onRate="onrate" :value="value"/>
```

```js
new Vue({
  el: '#app',
  components: { Rate },
  template: '<Rate @onRate="onrate" :value="value"/>',
  data: {
    value: '2.6'
  },
  methods: {
    onrate (num) {
      console.log(num)
      this.value = num
    }
  }
})
```
![](./img/06.gif)


## License

MIT.