对于单个文件，例如：`Example1.rs`，可以直接在终端中使用`rustc 文件名`，进行编译，会生成一个和文件名同名的可执行文件，使用`./可执行文件`，即可运行程序

但是，对于多个文件，或者需要依赖其他的函数的项目，上面这种编译运行方式，显然过于麻烦，因此，可以使用**cargo**，这个rust下的包管理工具

在终端中，使用`cargo new 项目名`，会在当前目录下生成一个Rust项目，

```
learning_rust/
├── Cargo.toml
├── Cargo.lock
├── .gitignore
└── src/
    └── main.rs
```

- Cargo.toml

```rust
[package]
name = "learning_rust" // 项目（包（crate））的名称，也就是你在 Cargo.toml 中定义的项目名。例如，这里你的 crate 名叫 learning_rust。编译后默认生成的可执行文件或库的名称也会是这个

version = "0.1.0" // 当前包的版本号（遵循语义化版本规范，例如 0.1.0）

edition = "2024" // Rust 的语言版本（例如 2018、2021、2024），决定编译器启用哪些语法特性


[dependencies]
```



- **当你构建项目时**，`cargo build`，生成的二进制或库文件会以这个名字命名（例如 learning_rust 或 liblearning_rust.rlib）

    在生产环境中，通常使用`cargo build --release`，构建release包，相比起默认的debug包，它的构建（编译）时间更长，因为期间会做一些优化，使程序运行得更快

- **当别人通过 Cargo 使用你的包时**，也会通过这个名字引用，比如：

    ```rust
    [dependencies]
    learning_rust = "0.1.0"
    ```

`cargo run`会构建项目，并直接运行生成的可执行文件。在`run`，或`build`后，在项目目录下，会生成一个*target*的目录，默认其中会有一个*debug*目录，里面有生成的可执行文件







