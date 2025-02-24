# How to work with Git & GitHub

Here are what steps you need to take to work with Git, GitHub, and GitHub Classroom:

1. Create a folder on your desktop, rename it to "Labs" and open up the command prompt (terminal).
2. Type in "cd " and drag and drop the folder you just created to the terminal window.
3. Then, type in "git clone <URL-to-repo>" and add your URL to the repository.
4. Now type in "cd " again and drag and drop the folder you just cloned to the terminal window. Leave this window open.
5. Do the assignment!
6. Once you are done, go back to the terminal window and type in "git status" to see what files need to be staged. The files will be in red.
7. Next, type in "git add ." to stage all files.
8.  Type in "git status" once again to see they are staged. The files should be green now.
9.  Next, type in "git commit -m "<YOUR-COMMENT>"" to commit the changes.
10. And lastly, type in "git push" to push your code to the remote repository on GitHub.
11. Now you can go to your GitHub repository page to check your resutls.

### **How to Install Git on Windows**  

#### **Step 1: Download Git for Windows**  
1. Go to the official Git website:  
   👉 [https://git-scm.com/downloads](https://git-scm.com/downloads)  
2. Click **"Download for Windows"** – It will automatically detect your Windows version (64-bit/32-bit).  
3. Once the installer (`.exe` file) is downloaded, open it.  

---

#### **Step 2: Install Git**
1. **Run the installer** and follow the setup wizard.  
2. **Choose the installation location** (default is `C:\Program Files\Git`). Click **Next**.  
3. **Select components** (leave default selections unless you need specific options). Click **Next**.  
4. **Choose default editor** (Select **Notepad++**, **VS Code**, or **Vim**). Click **Next**.  
5. **Adjust PATH environment**  
   - Choose **"Git from the command line and also from 3rd-party software"** (recommended).  
   - Click **Next**.  
6. **Choose HTTPS transport backend**  
   - Select **"Use the OpenSSL library"** (default). Click **Next**.  
7. **Choose line-ending conversion**  
   - Select **"Checkout Windows-style, commit Unix-style line endings"** (recommended). Click **Next**.  
8. **Choose terminal emulator**  
   - Select **"Use MinTTY (default terminal for Git Bash)"**. Click **Next**.  
9. **Enable extra options** (default settings are fine). Click **Install**.  
10. **Wait for the installation to complete**, then click **Finish**.  

---

#### **Step 3: Verify Git Installation**  
1. Open **Command Prompt (cmd)** or **Git Bash**  
2. Run the following command:  

   ```sh
   git --version
   ```

   ✅ If Git is installed correctly, it will show a version number like:  
   ```
   git version 2.x.x
   ```

---

#### **Step 4: Configure Git (First-Time Setup)**
1. Set your username:  
   ```sh
   git config --global user.name "Your Name"
   ```
2. Set your email:  
   ```sh
   git config --global user.email "your.email@example.com"
   ```
3. Check your Git configuration:  
   ```sh
   git config --list
   ```

Now you're ready to use Git on Windows! 🎉 🚀




### **How to Clone a Repository from GitHub**  

#### **Step 1: Copy the Repository URL**
1. Go to the GitHub repository you want to clone.  
2. Click on the **"Code"** button (Green button).  
3. Copy the **HTTPS URL** (e.g., `https://github.com/your-username/repo-name.git`).  

---

#### **Step 2: Open Terminal (Command Line)**
- On **Windows**: Open **Git Bash** or **Command Prompt** (`cmd`).  
- On **Mac/Linux**: Open **Terminal**.  

---

#### **Step 3: Navigate to the Folder Where You Want to Clone the Repo**
Use the `cd` command to change to your desired directory.  
For example, to clone into the **Documents** folder:  

```sh
cd ~/Documents
```

---

#### **Step 4: Clone the Repository**
Run the following command:  

```sh
git clone https://github.com/your-username/repo-name.git
```
---

#### **Step 5: Navigate into the Cloned Repository**
After cloning, move into the project folder:  

```sh
cd repo-name
```

---

#### **Step 6: Verify the Cloning Was Successful**
Run:  
```sh
git status
```
If the repository is successfully cloned, it will show:  
```
On branch main
Your branch is up to date with 'origin/main'.
```

Now you're ready to start working on your cloned GitHub repository! 🚀

### **How to Push Your Local Code to GitHub**
To push your local code to GitHub using the command line, follow these steps:

### **1. Initialize Git (if not already initialized)**
Navigate to your project folder in the terminal and run:
```sh
cd /path/to/your/project  # Change to your project directory
git init  # Initialize a new Git repository
```

### **2. Connect to GitHub Repository**
If you haven't already created a GitHub repository, create one at [GitHub](https://github.com/) and copy the repository URL.

Then, link your local repository to GitHub:
```sh
git remote add origin https://github.com/your-username/your-repository.git
```
To verify the remote repository, run:
```sh
git remote -v
```

### **3. Add and Commit Your Code**
```sh
git add .  # Adds all files to staging
git commit -m "Initial commit"  # Commit with a message
```

### **4. Push Code to GitHub**
If this is your first push, set the main branch and push:
```sh
git branch -M main  # Rename the branch to main (if not already main)
git push -u origin main  # Push to GitHub
```

For subsequent pushes, use:
```sh
git push origin main
```

### **5. Authenticate (if prompted)**
If using HTTPS, GitHub may ask for your credentials. You can avoid this by setting up SSH authentication.

### **Dealing with Unrelated History Issue**

If you're getting the `fatal: refusing to merge unrelated histories` error because your local repository and the remote repository have completely different histories. This usually happens when:  
- Your local repository was initialized separately (e.g., with `git init`) and isn't linked to the remote repo.  
- The remote repository already has commits that don't share a common ancestor with your local commits.  

### **Solution 1: Allow Unrelated Histories (Recommended for First-Time Pull)**
If you are sure you want to merge the remote code with your local repository, use the `--allow-unrelated-histories` flag:  

```sh
git pull --allow-unrelated-histories https://github.com/your-repo-name.git main
```

This forces Git to merge the remote history with your local history.

---

### **Solution 2: Clone Instead of Pull (Recommended for Fresh Start)**
If you haven't committed anything locally yet, it's often easier to **delete your local folder** and re-clone the repository:

```sh
rm -rf FrontEndWebProgW2025/Day01  # CAREFUL: This deletes your local folder!
git clone https://github.com/your-repo-name.git
```

This way, you start with a fresh copy of the remote repository without history conflicts.

---

### **Solution 3: Add Remote & Fetch Manually (If You Already Have Local Commits)**
If you've made local commits that you don’t want to lose, you can **manually add the remote, fetch changes, and merge**:

```sh
git remote add origin https://github.com/your-repo-name.git
git fetch origin main
git merge origin/main --allow-unrelated-histories
```

This merges the remote `main` branch into your local branch.





