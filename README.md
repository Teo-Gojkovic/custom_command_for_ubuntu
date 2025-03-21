# How to Create Your Own Ubuntu Command

## Create a Bash File for Your Command

I recommend creating a directory to store your scripts or custom commands:

```bash
mkdir script && cd script
```

Now, let's create our command:

```bash
nano ~/helloworld
```

For this example, I will create a custom command for pushing my code to GitHub.

```bash
#!/bin/bash

echo 'hello world'
```

> Press `Ctrl + X` to save and exit.

## Make Your Script Executable

We will use `chmod` to give execution rights to our file:

```bash
chmod +x ~/helloworld
```

## Copy the Script to a Directory in Your `$PATH`

Copy it to `/usr/local/bin` so you can run it from anywhere:

```bash
sudo cp ~/helloworld /usr/local/bin/helloworld
```

Now you can run your own command!
