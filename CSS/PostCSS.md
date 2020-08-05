# PostCSS

有关 CSS 的内容很多，但是基于我目前在使用的 Vue，查看了一下和 CSS 有关的内容，结合 Google 出来的信息，发现 PostCSS 做为一个入手点不错。

## PostCSS 是什么？

引用 [PostCSS](https://github.com/postcss/postcss) 对自己的定义：

> PostCSS is a tool for transforming styles with JS plugins. These plugins can lint your CSS, support variables and mixins, transpile future CSS syntax, inline images, and more.

在看各种介绍后，PostCSS 的介绍都会在开始非常多的介绍或者讲述自己是什么？不是什么？可是对新手可能不一定需要这么多信息，前面的定义够了，真正学了具备的功能，以及能做的事情，已经做出来的插件后作为一个入门者，然后再仔细品味这些可能更合适。另外一种就是在 CSS 领域已经接触了大量产品和做了大量工作的人，需要更快的建立对 PostCSS 认识的人，这些说明更重要。

这里可以快速的罗列一些结论，让我们有个全面的认识

-   PostCSS 不是预处理器，它可以选择像一个预处理器
-   PostCSS 不是后处理器，它可以选择像一个后处理器
-   PostCSS 可以促进对未来语法的支持，但它与“未来语法”无关
-   PostCSS 可以提供清理/优化功能，但是它不是清理/优化工具
-   PostCSS 并不是任何单一的东西；它具备无限的可能成为你选择它要具备的功能

它具备的特点

-   它能够通过插件生态系统获取各种功能
-   模块化，按需使用
-   极速处理能力
-   可以让你创建自己的插件
-   选择是否和常规 CSS 一起使用
-   可以不依赖预处理器库
-   可以与很多流行构建工具无缝部署
