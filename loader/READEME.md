- 用法

  - 简单用法

    >当一个 loader 在资源中使用，这个 loader 只能传入一个参数 - 这个参数是一个包含包含资源文件内容的字符串
    >
    >loader 会返回一个或者两个值。第一个值的类型是 JavaScript 代码的字符串或者 buffer。第二个参数值是 SourceMap，它是个 JavaScript 对象。

  - 复杂用法

    > 当链式调用多个 loader 的时候，请记住它们会以相反的顺序执行
    >
    > - 最后的 loader 最早调用，将会传入原始资源内容。
    > - 第一个 loader 最后调用，期望值是传出 JavaScript 和 source map（可选）。
    > - 中间的 loader 执行时，会传入前一个 loader 传出的结果。

- 相反顺序调用

- 写一个Loader遵循的规则

  - **简单易用**。
    - loaders 应该只做单一任务
  - 使用**链式**传递。
    - loader 可以被链式调用意味着不一定要输出 JavaScript。只要下一个 loader 可以处理这个输出，这个 loader 就可以返回任意类型的模块。
  - **模块化**的输出。
  - 确保**无状态**。
    - 确保 loader 在不同模块转换之间不保存状态
  - 使用 **loader utilities**。
    - `loader-utils`：它提供了许多有用的工具，但最常用的一种工具是获取传递给 loader 的选项
  - 记录 **loader 的依赖**。
  - 解析**模块依赖关系**。
  - 提取**通用代码**。
  - 避免**绝对路径**。
  - 使用 **peer dependencies**。