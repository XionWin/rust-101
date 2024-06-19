# Hello, Cargo!

`Cargo` is Rust's build system and package manager. Most rustaceans use this tool to manage their Rust projects because `Cargo` handles a lot of tasks for you, such as building your code, downloading the libraries your code depends on, and building those libraries. (We call the libraries that your code needs dependencies)

The simplest Rust programs, like the one we've written so far, don't have any dependencies. If we had built the "Hello, world!" project with `Cargo`, it would only use the part of `Cargo` that handles building your code.

Because the vast majority of Rust projects use `Cargo`, the rest of this book assumes that you're using `Cargo` too. `Cargo` comes installed with Rust if you used the official installer discussed in the "Installation" section. If you installed Rust through some other means, check whether `Cargo` is installed by entering the following in your terminal:

    $ cargo --version

If you see a version number, you have it! If you see an error, such as `command not found`, look at the documentation for your method of installation to determine how to install `Cargo` separately.
