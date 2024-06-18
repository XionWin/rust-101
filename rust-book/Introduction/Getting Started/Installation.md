# Installation
The first step is to install Rust. We'll download Rust through `rustup`, a command line tool for managing Rust versions and associated tools. You'll need an internet connection for the download.

    Note: If you prefer not to use `rustup` for some reason, please see the `Other Rust Installation Methods Page` for more options.

The following steps install the latest stable version of the rust compiler. Rust's stability guarantees ensure that all the examples in the book that compile will continue to compile with newer Rust versions. The output might differ slightly between versions because Rust often improves error messages and warnings. In other words, any newer, stable version of Rust you install using these steps should work as expected with the content of this book.

    Command line Notation
    In this chapter and throught the book, we'll show some commands used in the terminal. Lines that you should enter in a terminal all start with `$`. you don't need to type the `$` character; it's the command line prompt shown to indicate the start of each command. Lines that don't start with `$` typically show the output of the previous command. Additionally, PowerShell-specific examples will use `>` rather than `$`.

## installing rustup on Linux or macOS

If you're using Linux or macOS, open a terminal and enter the following command:
```
$ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf |sh
```
The command downloads a script and starts the installation of the `rustup` tool, which installs the latest stable version of Rust. You might be prompted for your password. If the install is successful, the following line will appear:

    Rust is installed now. Great!

You will also need a linker, which is a program that Rust uses to join its compiled outputs into one file. It is likely you already have one. If you get linker errors, you should install a C compiler, which will typically include a linker. A C compiler is also useful because some common Rust packages depend on C code and will need a C compiler.
On macOS, you can get a C compiler by running:
```
xcode-select --install
```
Linux users should generally install GCC or Clang, according to their distribution's documentation. For example, if you use Ubuntu, you can install the `build-essential` package.

## Installing rustup on Windows
On Windows, go to https://www.rust-lang.org/tools/install and follow the instructions for installing Rust. At some point in the installation, you'll receive a message explaining that you'll also need the MSVC build tools for Visual Studio 2013 or later.
To acquire the build tools, you'll need to install `Visual Studio 2022`. When asked which workloads to install, include:

* Desktop Development with C++
* The Windows 10 or 11 SDK
* The English language pack component, along with any other language pack of your choosing

The rest of this book use commands that work in both `cmd.exe` and PowerShell. If there are specific differences, we'll explain which to use.

## Troubleshooting
To check whether you have Rust installed correctly, open a shell and enter this line:

    $ rustc --version

If you see this information, you have installed Rust successfully! If you don't see this information, check that Rust is in your `%PATH%` system variable as follows.

In Windows CMD, use:

    > echo %PATH%

In PowerShell, use:

    > echo $env:Path

In Linux and macOS, use:

    $ echo $PATH

If that's all correct and Rust still isn't working, there are a number of places you can get help. Find out how to get in touch with other Rustaceans(a silly nickname we call ourselves) on the community page.

## Updating and Uninstalling

Once Rust is installed via `rustup`, updating to a newly released version is easy. From your shell, run the following update script:

    $ rustup update

To uninstall Rust and `rustup`, run the following uninstall script from your shell:

    $ rustup self uninstall

## Local Documentation

The installation of Rust also includes a local copy of the documentation so that you can read it offline. Run `rustup doc` to open the local documentation in your browser.

Any time a type or function is provided by the standard library and you're not sure what it does or how to use it, use the application programming interface(API) documentation to find out!


📗: Tue 18 Jun 2024 03:27:41 PM CST

