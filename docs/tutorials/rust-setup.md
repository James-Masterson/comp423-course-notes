# Rust Setup

* Primary author: [James Masterson](https://github.com/James-Masterson)
* Reviewer: [Ram Ariga](https://github.com/bariga04)

Hello Readers! The following tutorial is a guide to create a simple project in the programming language Rust.
Follow the steps as listed and you'll be on your way to making a Rust program in no time!

## Prerequisites:
1. Programming experience
2. Git installed: can install it here
3. Have VSCode installed
4. A command terminal
5. A GitHub account
6. Docker installed

## Step 1. Setting up your project  

Open your command terminal and `cd` to your home directory. Then make a new directory and cd into it.
!!! note  
    This should be your project root folder  

```bash  
cd  
mkdir <directory name>  
cd <directory name> 
``` 
Setup GitHub:
Create a git repository with this command:
```bash  
  git init
```

Then create a GitHub repository on the GitHub website by going to the repositories page and clicking the `new` button.
Make sure to NOT initialize with a .gitignore or license or README.md
Make sure to then link your local git repository to the remote repository in your GitHub acccount with this subcommand:
```bash
git remote add origin <link to repository>.git  
```

## Step 2. Create your dev container
Install the Dev Containers extension on VSCode
Open up your project folder in VSCode
Create a new directory called `.devcontainer` and a file inside of it called `devcontainer.json`
The `devcontainer.json` file will contain configurations for the container. In this case we will have a image and extensions that correlate with the Rust programming language. This file will also install the Rust extension in VSCode.
The devcontainer.json file should look something like this:
```js
{
  "name": "<Project Name>",  
  "image": "mcr.microsoft.com/devcontainers/rust:latest",  
  "customizations": {  
    "vscode": {  
      "settings": {},  
      "extensions": ["rust-lang.rust-analyzer"]  
    }  
  },  
  "postCreateCommand": "rustc --version"  
}  
```
!!! warning  
    After you finish your `devontainer.json` file make sure to save it.

Then reopen the project in the container. VSCode should prompt you to do this but if not use `Ctrl+Shift+P` then type **"Dev Containers: Reopen in Container"** in the search bar then select the option it shows.


## Step 3. Creating a Rust "Hello Comp423" program
Before starting the next step, make sure you have an up to date version of Rust installed using the `rustc --version subcommand`
Open up a new terminal in VSCode. You will be using this terminal from now on.
First use the `cargo new` subcommand to create a new Rust project. Name it the same name as your project if you'd like for convenience.
```bash
cargo new hello_comp423  
cd hello_comp423  
```
In your project's `src` folder, open the `main.rs` file. Replace its contents with the following:

!!! note  
    Your file should contain the following:  
    rust  
    fn main() {  
      println!("Hello COMP423");  
    }  


## Step 4. Run your program!

First use the `cargo build` subcommand before running your program  

!!! warning  
    make sure your current working directory is the rust program folder  

Now that you have your Rust project set up, you can run your program using the cargo run subcommand!
!!! note  
    Type the following in your VSCode terminal:

```bash
cargo run  
```

If you did everything correctly you should see **Hello COMP423** displayed in the terminal.
Using rustc directly:
An alternative way to compile and run the program is to use the rustc command directly. This is similar to using `gcc` for C programs, where you compile the source code into an executable.
This differs from the `cargo run` subcommand as `cargo run` handles both compilation and execution in one step, along with managing dependencies.
The following terminal commands detail the process:

```bash
rustc src/main.rs  
./main  
```

!!! note  
    This should also print Hello COMP423

Clean up build artifacts:
!!!  warning  
    Use the cargo clean subcommand to remove the target directory and all compiled artifacts.

Congrats on making it to the end! You're officially a Rust programmer!