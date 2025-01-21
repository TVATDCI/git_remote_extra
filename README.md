# git_remote_extra

## Setting Up Your Git Credentials

Follow these steps to set up your Git credentials:

1. **Enter your GitHub username:**

   ```bash
   git config --global user.name "Your GitHub Username"
   ```

2. **Enter the email you used to sign up for GitHub:**

   ```bash
   git config --global user.email "your@email.com"
   ```

3. **Change the default branch name to `main` (Very Important):**

   ```bash
   git config --global init.defaultBranch main
   ```

4. **Verify your configuration:**

   ```bash
   git config --list
   ```

   The terminal should display something like this:

   ```bash
   user.name=Your GitHub Username
   user.email=your@email.com
   init.defaultbranch=main
   ```

## Generating an SSH Key

To securely connect to GitHub, generate an SSH key:

1. **Generate the SSH key:**

   ```bash
   ssh-keygen -t ed25519 -C "your@email.com"
   ```

   Press Enter to accept the default file location and leave the passphrase empty for simplicity.

2. **Display the SSH key:**

   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

3. **Copy the displayed SSH key and add it to your GitHub account:**

   - Go to [GitHub SSH keys settings](https://github.com/settings/keys).
   - Click the "New SSH key" button.
   - Paste your SSH key into the "Key" field and give it a descriptive title.
   - Click the "Add SSH key" button.

   ![New SSH Key Button](sshbutton.png)
   ![Add SSH Key](newsshsubmit.png)

4. **Test your SSH connection:**

   ```bash
   ssh -T git@github.com
   ```

   If prompted, type `yes` to continue connecting. You should see a message like:

   ```bash
   Hi username! You've successfully authenticated, but GitHub does not provide shell access.
   ```

## Creating a New Repository

1. **Create a new repository on GitHub:**

   - Go to [GitHub](https://github.com) and click the "New" button to create a new repository.
   - Fill out the repository name and description, and choose whether it should be public or private.
   - Click the "Create repository" button.

2. **Initialize a new Git repository locally:**

   ```bash
   git init
   ```

3. **Add your remote repository:**

   ```bash
   git remote add origin git@github.com:yourusername/your-repo-name.git
   ```

4. **Add and commit your files:**

   ```bash
   git add .
   git commit -m "Initial commit"
   ```

5. **Push your changes to GitHub:**

   ```bash
   git push -u origin main
   ```

Congratulations! You have successfully set up your Git credentials, generated an SSH key, and created a new repository on GitHub. Enjoy coding and collaborating with GitHub!
