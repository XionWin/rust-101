# Hello, Cargo!

`Cargo` is Rust's build system and package manager. Most rustaceans use this tool to manage their Rust projects because `Cargo` handles a lot of tasks for you, such as building your code, downloading the libraries your code depends on, and building those libraries. (We call the libraries that your code needs dependencies)

The simplest Rust programs, like the one we've written so far, don't have any dependencies. If we had built the "Hello, world!" project with `Cargo`, it would only use the part of `Cargo` that handles building your code.

Because the vast majority of Rust projects use `Cargo`, the rest of this book assumes that you're using `Cargo` too. `Cargo` comes installed with Rust if you used the official installer discussed in the "Installation" section. If you installed Rust through some other means, check whether `Cargo` is installed by entering the following in your terminal:

    $ cargo --version

If you see a version number, you have it! If you see an error, such as `command not found`, look at the documentation for your method of installation to determine how to install `Cargo` separately.

## Creating a Project with Cargo

Let's create a new project using `Cargo` and look at how it differs from our original "Hello, world!" project. Navigate back to your projects directory (or wherever you decided to store your code). Then, on any operating system, run the following:
```
$ cargo new hello_cargo
$ cd hello_cargo
```
The first command creates a new directory and project called `hello_cargo`. We've named our project `hello_cargo`, and Cargo creates its files in a directory of the same name.

Go into the `hello_cargo` directory and list the files. You'll see the `Cargo` has generated two files and one directory for us: a `Cargo.toml` file and a `src` directory with a `main.rs` file inside.

It has also initialized a new Git repository along with a `.gitignore` file. Git files won't be generated if you run `cargo new ` within an existing `Git` repository; you can override this behavior by using `cargo new --vcs-git`.

    Note: Git is a common version control system. You can change `cargo new' to use a different version control system or no version control system by using the `--vsc` flag. Run `cargo new --help` to see the avaliable options.

Open `Cargo.toml` in your text editor of choice. It should look similar to the code in List 1-2.

Filename: `Cargo.toml`
```
[package]
name = "hello_cargo"
version = "0.1.0"
editor = "2021"

# See more keys and their definations at https://doc.rust-lang.org/cargo/reference/manifest.html

[dependencies]
```
This file is in the `TOML`(Tom's Obvious, Minimal Language) format, which is Cargo's configuration format.

The first line, `[package]`, is a section heading that indicates that the following statements are configuring a package. As we add more information to this file, we'll add other sections.

The next three lines set the configuration information `Cargo` needs to compile your program: this name, the version, and the edition of Rust to use. We'll talk about the `edition` key in `Appendix E`.

The last line `[dependencies]`, is the start of a section for you to list any other crates dependencies. In Rust, package of code are referred to as `crates`. We won't need any other crates for this project, but we will in the first project in Chapter 2, so we'll use this dependencies section then.

Now open `src/main.rs` and take a look:

Filename: `src/main.rs`
```
fn main() {
    println!("hello, world!");
}
```
`Cargo` has generated a "Hello, world!" project for you, just like the one we wrote in List 1-1! So far, the differences between our project and the project `Cargo` generated are the `Cargo` placed the code in the `src` directory and we have a `Cargo.toml` configuration file in the top directory.

`Cargo` expects your source files to live inside the `src` directory. The top-level project directory is just for `README` files, license information, configuration files, and anything else not related to your code. Using `Cargo` helps your organize your projects. There's a place for everything, and everything is in its place.

If you started a project that doesn't using `Cargo`, as we did with the "Hello, world!" project, you can convert it to a project that does use `Cargo`. Move the project code into the `src` directory and create an appropriate `Cargo.toml` file.

## Building and Running a Cargo Project

New let's look at what's different when we build and run the "Hello, world!" program with `Cargo`! From your `hello_cargo` directory, build your project by entering the following command:
```
$ cargo build
   Compiling hello_cargo v0.1.0 (file:///projects/hello_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 2.85 secs
```
This command creates an executable file in `target/debug/hello_cargo` (or `target/debug/hello_cargo.exe` on Windows) rather than in your current directory. Because the default build is a debug build, `Cargo` puts the binary in a directory named `debug`. You can run the executable with this command:
```
$ ./target/debug/hello_cargo # or .\target\debug\hello_cargo.exe on Windows
Hello, world!
```
If all goes well, `Hello, world!` should print to the terminal. Running `cargo build` for the first time also causes `Cargo` to create a new file at the top level: `Cargo.lock`. This file keeps track of the exact versions of dependencies in your project. This project doesn't have dependencies, so the file is a bit 📝sparse(|*spärs*| 稀;疏). You won't ever need to change this file manually; `Cargo` manages its contents for you.

We just built a project with `cargo build` and ran it with `./target/debug/hello_cargo`, but we can also use `cargo run` to compile the code and then run the resultant executable all in one command:
```
$ cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.0 secs
     Running `target/debug/hello_cargo`
Hello, world!
```
Using `cargo run` is more convenient than having to remember to run `cargo build` and then use the whole path to the binary, so most developers use `cargo run`.


