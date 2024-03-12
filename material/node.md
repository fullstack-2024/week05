# Node & npm


## NodeJS

Node.JS is Javascript Runtime Environment for running JavaScript files directly on a computer. JavaScript is built into every web browser, but if you want to run JavaScript directly without a browser, you need to install Node.JS.

Installing Node.js on macOS follows almost the same procedure as Windows. All you have to do is to download the installation file found [here](https://nodejs.org/en/download/). The installer will walk you through the rest.

NPM configuration:

1. Older MacOS (bash terminal)

```bash
            mkdir ~/.npm-packages
            npm config set prefix ~/.npm-packages
            echo NPM_PACKAGES="${HOME}/.npm-packages" >> ${HOME}/.bashrc
            echo prefix=${HOME}/.npm-packages >> ${HOME}/.npmrc
            echo NODE_PATH=\"\$NPM_PACKAGES/lib/node_modules:\$NODE_PATH\" >> ${HOME}/.bashrc
            echo PATH=\"\$NPM_PACKAGES/bin:\$PATH\" >> ${HOME}/.bashrc
            echo source "~/.bashrc" >> ${HOME}/.bash_profile
            source ~/.bashrc
```

2. Newer MacOS (zsh terminal)

```bash
            mkdir ~/.npm-packages
            npm config set prefix ~/.npm-packages
            echo NPM_PACKAGES="${HOME}/.npm-packages" >> ${HOME}/.zshrc
            echo prefix=${HOME}/.npm-packages >> ${HOME}/.npmrc
            echo NODE_PATH=\"\$NPM_PACKAGES/lib/node_modules:\$NODE_PATH\" >> ${HOME}/.zshrc
            echo PATH=\"\$NPM_PACKAGES/bin:\$PATH\" >> ${HOME}/.zshrc
            echo source "~/.zshrc" >> ${HOME}/.zsh_profile
            source ~/.zshrc
```

---
## Homebrew (For Mac Only)

Homebrew is a piece of software for macOS that lets you install extra unix
software on your Mac.

Head to the [homebrew](#links) website and follow the instructions on
the main page.

You will see instructions to run a command like this, so open a Terminal and run this:

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

After some output it should print out that homebrew is installed successfully.

You can always check homebrew for possible problems by typing this:

```shell
brew doctor
```

---
## Git

### Windows

You can easily install `Git` in Windows by using the installer found [here](#links).

Once you've downloaded one of the "Git for Windows Setup" distributions (either
32-bit or more likely 64-bit) you can launch the installer and accept all the
defaults.

### Mac

Mac comes with some tools by default. Git is one that you want to make sure is up
to date so you can run the following in your terminal.

```shell
xcode-select --install
```

## Configuring git

Once you have installed git, configure the information that gets logged for each
of your commits by updating the default (global) credentials that git uses. (You
could overwrite these credentials temporarily per local repo. While that
shouldn't be necessary, it is helpful to know that it is an option.) You will also want to set the default branch to `main`.

In your terminal, run

```shell
git config --global user.name "Your Name"
git config --global user.email "Your Email"
git config --global init.defaultBranch main
```

Check that your name and email have been set up correctly by using the following commands:

```shell
git config user.name
git config user.email
```

You should see your name and email address returned. Repeat this step if there
are any errors.






<!--  -->
[upgrade npm]:https://docs.npmjs.com/try-the-latest-stable-version-of-npm