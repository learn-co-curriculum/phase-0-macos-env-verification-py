# Verify and Troubleshoot your MacOS Environment Setup

## Action Item

1. Open your "Terminal" application using "Spotlight Search"
2. Run the following command:

```console
$ curl -so- https://raw.githubusercontent.com/learn-co-curriculum/flatiron-manual-setup-validator/master/macos-phase-0-validation.sh | zsh 2> /dev/null
```

## Check Your Work

<iframe width="560" height="315" src="https://www.youtube.com/embed/CNuoCmve-xc" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Note: your output from the verification script may include some different checks
than are shown in the video. Do not be concerned if that's the case — the
information in the video still applies.

If all checks pass, you have completed your environment setup and are ready to
move on!

If something does not pass, that is okay. Revisit the installation instructions
for the item that did not pass. If you are able to run the commands listed in
the **Check Your Work** section for that item, this may just be an issue with
the validator.

## Troubleshooting

### Fixing NVM Dotfile Issues for MacOS

If you are having trouble getting NVM or Node to work, you may have an
issue with your `.zshrc` file. To fix, we need to run two commands.

The first command makes a backup of your current `.zshrc` file:

```console
$ mv ~/.zshrc{,.bak}
```

The second command replaces the contents of your `.zshrc` file with a default
dot file:

```console
$ curl -sSL https://raw.githubusercontent.com/flatiron-school/dotfiles/master/.zshrc-no-ruby > ~/.zshrc
```

Close and reopen your terminal. With a new `.zshrc` file, we can now test out
each tool.

### Verify NVM is installed

To confirm NVM is installed, run:

```console
$ nvm
```

If you see a message ending with `"Note: to remove, delete, or uninstall nvm…"`, NVM is installed.

> If the `nvm` command is not recognized or you see an error
> `complete:13: command not found: compdef`, run the following command:
>
> ```console
> $ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
> ```

### Verify Node is Installed

To confirm Node is installed, run:

```console
$ nvm list
```

If you see a message starting with "-> v14.13.0" (or any number higher than
this), a version of Node is installed that will work for this course.

> If you don't see this number, install the newest version of Node:
>
> ```console
> $ nvm install node
> ```
