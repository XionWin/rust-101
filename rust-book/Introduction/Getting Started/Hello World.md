# Hello, World!

Now that you've installed Rust, it's time to write your first Rust program. It's traditional when learning a new language to write a little program that print the text `Hello, world!` to the screen, so we'll do the same here!

    Note: This book assumes basic familiarity with the command line. Rust makes no specific demands about your eidting or tooling or where you code lives, so fi you prefer to use an integrated development environment (IDE) instead of the command line, feel free to use your favorite IDE. Many IDEs now have some degree of Rust support; check the IDE's documentation for details. The Rust team has been focusing on enabling great IDE support via `rsut-analyzer`. See Appendix D for more details.

## Creating a Project Directory

You'll start by making a directory to store your Rust code. It doesn't matter to Rust where your code lives, but for the exercises and projects in this book, we suggest making a projects directory in you home directory and keeping your projects there.

Open a terminal and enter the following commands to make a projects directory and a directory for the "Hello, world!" project within the projects directory.

For Linux, macOS, and PowerShell on Windows, enter this:
```
$ mkdir ~/projects
$ cd ~/projects
$ mkdir hello_world
$ cd hello_world
```
For Windows CMD, enter this:
```
> mkdir "%USERPROFILE%\projects"
> cd /d "%USERPROFILE%\projects"
> mkdir hello_world
> cd hello_world
```

## Writing and Running a Rust program

Next make a new source file and call it `main.rs`. Rust files always end with the `.rs` extension. If you're using more than one word in your filename, the convention is to use an underscore to separate them. For example, use `hello_world.rs` rather than `helloworld.rs`.

Now open the `main.rs` file you just created and enter the code in Listing 1-1.

Filename: main.rs
```
fn main() {
  println!("Hello world!");
}
```
Listing 1-1: A program that prints `Hello, world!`

Save the file and go back to your terminal window in the `~/projects/hello_world` directory. On Linux or macOS, enter the following commands to compile and run the file:
