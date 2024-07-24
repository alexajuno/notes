# Git Branching

## 3.1 Branches in a nutshell

### Branches in a nutshell

- Each file that changed has a blob, and each commit is record of those blobs's id

### Creating new branch

- git branch &lt;branch-name&gt;
  
### Switch Branches

- git checkout &lt;branch-name&gt;

## 3.2 Basic branching and merging

### Branching

- git checkout -b &lt;branch-name&gt;
- git merge after switching to the branch you want to merge 

### Basic merging

- git branch -d &lt;branch-name&gt;

### Basic Merge Conflicts

- git mergetool

## 3.3 Branch Management

- git branch [-v]
- git branch --move git branch --move bad-branch-name corrected-branch-name
- git push --set-upstream origin corrected-branch-name
- git push origin --delete bad-branch-name

## 3.4 Branching workflow

- 