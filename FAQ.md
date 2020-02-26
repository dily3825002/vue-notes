### FAQ

* template
* computed
* mapState
* mapMutations

### 解构赋值

解构赋值概念：在ES6中，直接从数组和对象中取值，按照对应位置，赋值给变量的操作

```
// ES6 之前
let a = 1;
let b = 2;

// ES6 之后
let [a, b] = [1, 2];
```

### 拓展运算符

拓展运算符使用(...)，类似rest参数的逆运算，将数组转为用(,)分隔的参数序列

```
function f (a, b){
    console.log(a, b);
}
f(...[1, 2]); // 1 2
```

### 同名属性

```
let a = 'a1';
let b = { a };  // b => { a : 'a1' }
// 等同于
let b = { a : a };
```

### vuex

* State
    * mapState：当一个组件需要获取多个状态时候，将这些状态都声明为计算属性会有些重复和冗余。为了解决这个问题，我们可以使用 mapState 辅助函数帮助我们生成计算属性
* Getters
    * mapGetters：mapGetters 辅助函数仅仅是将 store 中的 getter 映射到局部计算属性
    * …这个符号是ES2015的一个新的语法糖，即将mapGetters处理后的内容展开后填入
* Mutations
    * mapMutations：将组件中的 methods 映射为 this.$store.commit
    * 这样映射后就不用调用 this.$store.commit('increment')了

### 项目结构

```
├── index.html
├── main.js
├── api
│   └── ... # 抽取出API请求
├── components
│   ├── App.vue
│   └── ...
└── store
    ├── index.js          # 我们组装模块并导出 store 的地方
    ├── actions.js        # 根级别的 action
    ├── mutations.js      # 根级别的 mutation
    └── modules
        ├── cart.js       # 购物车模块
        └── products.js   # 产品模块
```        

### 严格模式

需要打开

```
const store = new Vuex.Store({
  // ...
  strict: true
})
```
