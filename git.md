# Git Config 
```
git config --global user.name "Stefano P." 
git config --global user.email "s*@gmail.com"
```

In VSC, after opening the folder type in terminal 

```
git init 
```

## Git Environments 
### Staging Files

```
git add FILENAME 
git add --all
git add -A
git add .
```


### Commit Files 
```git commit -m "First Commit"```

The committ information contains 
- a hash id that identifies the unique commit
- an indication of in which the head resides. Often you'll see main or master 

The head always points to the current reality aka the branch


### Checking the commits 
```git log```

You will see the hex code for the commit 

### Restoring Files 
```
git restore README.md 
# git restore .
# git checkout . 
```


### Check which branch you are on 
```
git status 
```

And bring staged files back 
```
git restore --staged README.md
```

### Select what you want to ignore (.gitignore)
A folder needs to to have / at the end . It's a file within which you put the content you want to ignore e.g. .DS_store , .vscode/

You can also set a **Global Ignore File** with 
```
git config --global core.excludesfile [file]
```

### Clearing the cache 
```
git rm -r --cached
```

### Amending 

```
git commit -amend 
git commit -am "new commit message" 
git commit -amend --no-edit
```

### Deleting

1. Way one: You can delete the file. In this case it records the deletion but as something that you need to add into staging. You would need to git add and if you want to restore git restore . 
2. Way two: git RM file but here the deletion is already into staging so ready to commit. It saves us a step. 

To undo it you will have to 
```
git restore -S file.html. 
```
Git restore again because you need to take it away from staging 

### Renaming

If you just change the name for the file it will be marked as a deletion and addition. To undo this it's a bit harder 
```
Git MV oldfile.html new file.html
```

It saves us the step of staging the file and we can go to commit directly. To restore you  want to reverse the naming 
```
Git mv newname.html oldname.html
```

MV = move, it's a legacy name from Linux . But remember moving is deleting a file and adding another one
 
 
###  Differences
``` 
 Git diff 
 ```
 
 It shows the differences between the two files. (Clear clears the terminal line). To exit hit Q
 Super hard to read in terminal. Use instead the source control editor in Visual Studio Code. 
 If you hit the plus sign in the editor you can already stage the changes And committ 
 
 To check changes you can use 
 ```
 Git log --oneline
 ```
 
Get git lense from the visual studio code market place 

### Amending 

to add small changes to a last committ 
```
Git commit --ammend -m "namecommit"
```

```
Git reset #hashid 
```

You move back the head to another commit but you will notice that the files are not changed. They stay as they are in the editor 

```
Git rest --hard #hashid
```

You rewind to a specific commit and get rid of the changes in the actual files 

### Rebasing 

you take the commit from a branch and apply them to another. You can rebase using ROOT or HEAD minus the number of commits
```
Git rebase -i root
```
You can also use the squash command, to merge the novel part with the original commit . Also you can use the fixup command so it doesn't keep both of the gir log messages 

### Branches  
```
Git branch
```
Lets you check out all the branches of your code 
 
```
  Git switch -c Nameofbranch 
 ```
 (In previous versions you could see git checkout -b NAME)
  
### Merging

It will change the branches from the current branch and add the changes from the other beanch .We switch back to main

```
Git switch main 
Git branch // we see we have two branches 
```

```
Git merge fix-classes 
```

You can check with ```Git log --oneline```


### Deleting a Branch 
When you are done with a feature or a change 
```
Git -d fix-classes
```
If you check Git branch. You only have main 

## Git Flow 
This way of working with branches 


* Feature branch ```Git switch -c Nameofbranch ```
* Make changes 
* Merge to master ```Git merge fix-classes ```
* Delete old branch ```Git -d fix-classes```

### Merge Conflicts 




