### Git Commands Cheat Sheet  

#### 1. Initialize Git  
```
git init
```

#### 2. Create a Repository  
```
gh repo create your-repo-name --public/private --source=. --remote=origin
```

#### 3. Add Files to Git (First Time)  
```
git add .
git commit -m "your commit message"
git push origin main
```

#### 4. Add Files to Git (Subsequent Commits)  
```
git add .
git commit -m "your commit message"
git push
```

#### 5. Switching Git Branches  
- Create and switch to a new branch:  
  ```
  git switch -c branch-name
  ```
  *(Use `-c` only if the branch does not exist.)*  
- Switch to an existing branch:  
  ```
  git switch branch-name
  ```
- View the current branch:  
  ```
  git branch
  ```

#### 6. Merge Branches  
- Merge a branch into `main` (or another target branch):  
  ```
  git checkout main
  git merge branch-name
  ```
- If merge conflicts occur, fix them, then run:  
  ```
  git add .
  git commit -m "Resolved merge conflicts"
  ```
- To abort a merge:  
  ```
  git merge --abort
  ```

#### 7. Link to an Existing Remote Repository  
- Add a remote repository:  
  ```
  git remote add origin "your-repo-link"
  ```
- Verify the remote repository:  
  ```
  git remote -v
  ```

#### 8. Remove Sensitive Information from Commit History  
- Open the interactive rebase manager:  
  ```
  git rebase -i --root
  ```
- Modify all affected commits as needed. Follow the provided Git instructions.  
- Before proceeding to the next commit, run:  
  ```
  git add .
  git commit --amend --no-edit
  ```
- After modifying all commits, ensure rebase data is removed:  
  ```
  Remove-Item -Recurse -Force .git/rebase-merge
  ```
- Relink the remote repository (see #7).  
- Force push the updated history:  
  ```
  git push --force origin main
  ```




