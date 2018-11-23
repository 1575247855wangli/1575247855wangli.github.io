---
title: vuex
date: 2018-11-23 10:06:00
tags: 
    -"vue"
categories: "vuex"
description: "vuex"
---
## Vuex 应用的核心是store 里面装的是数据源，vuex 的状态存储是响应式的，store变化，相应的组件也会发生变化
- 不能直接改变store的状态，唯一途径通过提交mutation
1 能理解能 state为data，mutations 相当于methods?
```javascript
const store = new Vuex.Store({
  state: {
    count: 0
  },
  mutations: {
    increment (state) {
      state.count++
    }
  }
})
store.state 获取对象，store.commit 状态改变
store.commit('increment') 触发事件 state.count
console.log(store.state.count)
```
# State 
- Vuex 使用单一状态树，每个应用仅仅包含一个store实例
- 在Vue组件中展示状态
  - 在计算属性中 computed:{
      count () {
          return store.state.count
      }
  }
  - 在根组建中使用 Vue.use(Vuex)
  1 子组件能通过this.$store访问到 例如this.$store.state.count
## mapState 辅助函数
```javascript
// 在单独构建的版本中辅助函数为 Vuex.mapState
import { mapState } from 'vuex'

export default {
  // ...
  computed: mapState({
    // 箭头函数可使代码更简练
    count: state => state.count,

    // 传字符串参数 'count' 等同于 `state => state.count`
    countAlias: 'count',

    // 为了能够使用 `this` 获取局部状态，必须使用常规函数
    countPlusLocalState (state) {
      return state.count + this.localCount
    }
  })
}
```
# Getter 相当于store的计算属性 返回值会根据依赖被缓存起来，只有依赖值发生改变才会被重新计算
```javascript
const store = new Vuex.Store({
  state: {
    todos: [
      { id: 1, text: '...', done: true },
      { id: 2, text: '...', done: false }
    ]
  },
  getters: {
    doneTodos: state => {
      return state.todos.filter(todo => todo.done)
    }
  }
})
store.getters.doneTodos 去获取这个返回值
# 通过属性访问
```
##mapGetters 辅助函数
```javascript
import { mapGetters } from 'vuex'

export default {
  // ...
  computed: {
  // 使用对象展开运算符将 getter 混入 computed 对象中
    ...mapGetters([
      'doneTodosCount',
      'anotherGetter',
      // ...
    ])
  }
}
```
- 如果你想将一个 getter 属性另取一个名字，使用对象形式

#接受 state 作为第一个参数
- 接受 state 作为第一个参数 方法调用为store.commit('increment')
- 提交载荷（Payload）载荷应该是一个对象，这样可以包含多个字段并且记录的 mutation 会更易读
```javascript
mutations: {
  increment (state, payload) {
    state.count += payload.amount
  }
}
// 调用的时候为
store.commit('increment', {
  amount: 10
})

store.commit({
  type: 'increment',
  amount: 10
})
```
Mutation 必须是同步函数
一条重要的原则就是要记住 mutation 必须是同步函数
# action action包含处理异步
- Action 函数接受一个与 store 实例具有相同方法和属性的 context 对象，因此你可以调用 context.commit 提交一个 mutation，或者通过 context.state 和 context.getters 来获取 state 和 getters。
- 分发 Action
```javascript
// 以载荷形式分发
store.dispatch('incrementAsync', {
  amount: 10
})
```
- 组合 Action store.dispatch 可以处理被触发的 action 的处理函数返回的 Promise，并且 store.dispatch 仍旧返回 Promise