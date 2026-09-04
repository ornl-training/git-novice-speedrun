---
title: "Setup Instructions"
teaching: 0
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions 

- What software do I need to have installed?
- Do I have a GitLab account?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Install VS Code and other needed software
- Connect VS Code to code.ornl.gov

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: callout

If you are participating in this workshop remotely (e.g. over Zoom), it is highly recommended that you use two screens: 1 screen with the remote meeting, to see the instructor sharing their screen, and 1 screen with your applications. You will need to have VS Code and a web browser open to https://code.ornl.gov in order to follow along.

:::::::::::::::::::::::::::::::::::::

## Software Installations

### Visual Studio Code

[Download and install VS Code](https://code.visualstudio.com/download). 

If you are new to using VS Code, you can review this [Getting Started](https://code.visualstudio.com/docs/getstarted/getting-started) guide.

### Git

You must have Git installed on your local computer. Typically, Mac and Linux computers come pre-installed with git, while Windows users must install [GitBash](https://gitforwindows.org) (Git for Windows). However, you should verify that Git is installed on your computer.

You can verify git is installed by opening a command line application (e.g. Terminal) and typing: 

```bash
$ git version
```

If you see an error message stating git is an unknown command, you will need to install git.

If you do not already have git installed, you can refer to [this GitHub guide](https://github.com/git-guides/install-git) on installing git for any OS. 

### Bash

You should have a Bash terminal. If you are on a Windows, you will have a Bash terminal by virtue of installing Git for Windows (GitBash). If you are on a Mac or Linux, you will already have a Bash terminal. If you prefer, you can use a similar terminal like Zsh.

Rather than using a seperate command line application, you will be using the Terminal in VS Code. To learn more about using the Terminal in VS Code, refer to [these docs](https://code.visualstudio.com/docs/terminal/basics).

## Connect VS Code to code.ornl.gov

First, you will need to open the [GitLab SSH Keys Page](https://code.ornl.gov/-/user_settings/ssh_keys) and click "Add new key". You will need to provide a private key to this form that can be generated with:

```bash
ssh-keygen -t ed25519 -C "your_email@ornl.gov"
```

It will ask you a few questions, but the defaults are sufficient for our purposes. Once done, it will write a file to `$HOME/.ssh/id_ed25519`. You can read this file with:

```bash
cat $HOME/.ssh/id_ed25519
```

Copy the contents of the file with your computer's clipboard, paste it into the GitLab form, and click "Add key". Finally, we need to tell our computer to use this key when communicating with GitLab. We can do this by creating a file at `$HOME/.ssh/config` with the following contents:

```code
Host code.ornl.gov
  PreferredAuthentications publickey
  IdentityFile /Users/qid/.ssh/id_ed25519
```

With this, your computer should be configured to communicate with GitLab properly.

:::::::::::::::::::::::::::::::::::::::: keypoints

- GitHub, VS Code, bash, and git are needed for this lesson

::::::::::::::::::::::::::::::::::::::::::::::::::