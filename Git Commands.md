### **Git Commands Cheat Sheet**  

#### **1. Initialize Git**  
```sh
git init
```

#### **2. Create a Repository**  
```sh
gh repo create your-repo-name --public/private --source=. --remote=origin
```

#### **3. Add Files to Git (First Time)**  
```sh
git add .
git commit -m "your commit message"
git push -u origin main
```

#### **4. Add Files to Git (Subsequent Commits)**  
```sh
git add .
git commit -m "your commit message"
git push  
# Use --force if you want to overwrite remote changes (⚠️ risky), 
# or run git pull first to sync and avoid conflicts.
```

#### **5. Switching Git Branches**  
- **Create and switch to a new branch:**  
  ```sh
  git switch -c branch-name
  ```
  *(Use `-c` only if the branch does not exist.)*  
- **Switch to an existing branch:**  
  ```sh
  git switch branch-name
  ```
- **View the current branch:**  
  ```sh
  git branch
  ```

#### **6. Merge Branches**  
- **Merge a branch into `main` (or another target branch):**  
  ```sh
  git checkout main
  git merge branch-name
  ```
- **If merge conflicts occur, fix them, then run:**  
  ```sh
  git add .
  git commit -m "Resolved merge conflicts"
  ```
- **To abort a merge:**  
  ```sh
  git merge --abort
  ```

#### **7. Link to an Existing Remote Repository**  
- **Add a remote repository:**  
  ```sh
  git remote add origin "your-repo-link"
  ```
- **Verify the remote repository:**  
  ```sh
  git remote -v
  ```

#### **8. Remove Sensitive Information from Commit History**  
- **Open the interactive rebase manager:**  
  ```sh
  git rebase -i --root
  ```
- **Modify all affected commits as needed. Follow the provided Git instructions.**  
- **Before proceeding to the next commit, run:**  
  ```sh
  git add .
  git commit --amend --no-edit
  ```
- **After modifying all commits, ensure rebase data is removed:**  
  ```sh
  Remove-Item -Recurse -Force .git/rebase-merge
  ```
- **Relink the remote repository (see #7).**  
- **Force push the updated history:**  
  ```sh
  git push --force origin main
  ```
