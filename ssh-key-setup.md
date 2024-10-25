# Setting Up SSH for GitHub

Follow these steps to set up SSH for your GitHub account.

## 1. Check for Existing SSH Keys
Open your terminal and run:

```bash
ls -al ~/.ssh
```

This will list any existing SSH keys. Look for files named `id_rsa` or `id_ed25519`.

## 2. Generate a New SSH Key (if needed)
If you don’t have an SSH key or want to create a new one, use the following command:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

If your system doesn't support `ed25519`, you can use:

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

Follow the prompts to save the key (you can press Enter to accept the default location) and set a passphrase if desired.

## 3. Add Your SSH Key to the SSH Agent
Start the SSH agent:

```bash
eval "$(ssh-agent -s)"
```

Then add your SSH key:

```bash
ssh-add ~/.ssh/id_ed25519
```

Or for RSA:

```bash
ssh-add ~/.ssh/id_rsa
```

## 4. Copy Your SSH Key to the Clipboard
Use the following command to copy your public SSH key:

```bash
pbcopy < ~/.ssh/id_ed25519.pub
```

Or for RSA:

```bash
pbcopy < ~/.ssh/id_rsa.pub
```

## 5. Add SSH Key to Your GitHub Account
1. Go to [GitHub](https://github.com) and log in.
2. Click on your profile picture in the top right corner, then go to **Settings**.
3. In the left sidebar, click **SSH and GPG keys**.
4. Click **New SSH key** or **Add SSH key**.
5. Paste your key into the "Key" field and give it a descriptive title.
6. Click **Add SSH key**.

## 6. Test Your SSH Connection
Finally, test your SSH connection with:

```bash
ssh -T git@github.com
```

You’re now ready to use SSH with GitHub! If you have any questions, feel free to ask!
```

Feel free to copy and modify it as needed!
