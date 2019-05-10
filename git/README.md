## Fixup

Keep your branch [clean with fixup][1] and autosquash

*git rebase i \<after-this-commit>*

 - `git commit --fixup <commit>` automatically marks your commit as a fix of a previous commit
 - `git commit --fixup :/foo` the most recent commit that contained the string foo in the first line of it’s commit message. 
 - `git rebase -i --autosquash` automatically organize merging of these fixup commits and associated normal commits

**Summary**  

 - `git commit --fixup <COMMIT THAT NEEDS FIXING>`
 - `git rebase -i --autosquash <FIRST COMMIT THAT NEEDS FIXING>~1`


## Moving commits

Let's say you are on `master` branch, and you want move some commits to another branch.   
It's important that you have NOT sync `master` branch.

 - On master branch `git checkout -b feature-a`
 - On master branch `git reset --hard <last commit SHA synced with remote>`


[1]: https://dev.to/koffeinfrei/the-git-fixup-workflow-386d

