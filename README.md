# How to Create Your Own Ubuntu Command

## Create a Bash File for Your Command

I recommend creating a directory to store your scripts or custom commands:

```bash
mkdir script && cd script
```

Now, let's create our command:

```bash
nano ~/pushcode
```

For this example, I will create a custom command for pushing my code to GitHub.

```bash
#!/bin/bash

# Check if the repository has been initialized
if [ ! -d ".git" ]; then
    echo "This is not a Git repository. Initializing..."
    git init
fi

# Ask for the GitHub repository URL
read -p "Enter your GitHub repository URL: " repo_url

# Set the remote origin
git remote add origin "$repo_url" 2>/dev/null || git remote set-url origin "$repo_url"

# Ask for a commit message
read -p "Enter commit message: " commit_msg

# Add, commit, and push
git add .
git commit -m "$commit_msg"
git push -u origin main 2>/dev/null || git push -u origin master

echo "Code pushed to GitHub successfully!"
```

> Press `Ctrl + X` to save and exit.

## Make Your Script Executable

We will use `chmod` to give execution rights to our file:

```bash
chmod +x ~/pushcode
```

## Copy the Script to a Directory in Your `$PATH`

Copy it to `/usr/local/bin` so you can run it from anywhere:

```bash
sudo cp ~/pushcode /usr/local/bin/pushcode
```

Now you can run your own command!
