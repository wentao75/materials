# Composition API （组合式 API）

这是 Vue3 新特性中最重要的一个部分，如果大家熟悉 React Hook，你也可以叫它 Vue Hook。

## 动机和目的

简单的描述：**低侵入、函数式 API，更灵活地组合组件逻辑。**
同时，目的中最主要也是面向更加复杂，更大的应用和软件项目考虑。

-   更好的逻辑复用与代码组织

大型项目实践，多人项目实践，长期迭代和维护条件下，如何保持 Vue 项目出现的问题：

1. 概念增长，代码阅读和理解的难度增加
2. 如何更加简洁且低成本的机制提取与重用多个组件之间的逻辑？

-   更好的类型推导

为了更好的支持 Typescript 过程中，原来的体系遇到了不小的麻烦。Vue 原有的设计没有考虑到类型推导的问题，适配 Typescript 非常麻烦！

使用 Typescript class 以及 decorator 模式来支持 Typescript 存在较大风险。

## 基本范例

我们从一个范例入手，了解下 Composition API 的基本结构和使用方法

    <template>
    <button @click="increment">
        Count is: {{ state.count }}, double is: {{ state.double }}
    </button>
    </template>

    <script>
    import { reactive, computed } from 'vue'

    export default {
        setup() {
            const state = reactive({
                count: 0,
                double: computed(() => state.count * 2),
            })


            function increment() {
                state.count++
            }

            return {
                state,
                increment,
            }
        },
    }
    </script>

整个 API 的引入需要关注这样几点

-   响应式状态与副作用
-   代码结构
-   复用和逻辑提取

### 响应式状态和副作用

看一下基本范例中对响应式状态的定义

    import { reactive, computed } from 'vue'

    // state 现在是一个响应式状态
    const state = reactive({
        count: 0,
    })

所谓响应式状态，和我们在 2.x 中利用 data 属性定义的状态是一样的，可以在模版渲染时使用。而在 DOM 中渲染内容会被视为一种“副作用”：程序在外部修改其本身（也就是这个 DOM）的状态。API 提供了`watchEffect`方法应用基于响应式状态的副作用，而且这个方法在内部包含的响应式状态发生变化时自动重新应用。下面就是一个基于前面定义的 state 响应状态的副作用

    watchEffect(() => {
        document.body.innerHTML = `count is ${state.count}`
    })
