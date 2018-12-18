`%` is the current file path
`Gread` Checkout the file and reload buffer
`Gwrite` add current file to stage
`Gcommit` 
`Gblame` 
`Gdiff` (Left side is stage, right is working)
  - on conflict file, left window is the target, middle is the working, right is the merge
  - `]c` and `[c` move bettwen changes
`Gstatus`  `-` will add/remove file from sage (you can select many files), `p` patch file, `enter` the file will be open, `shift C` will commit,
`diffget`: the the located change and move to working (undo change)
`Gedit`: Example `Gedit master:<File>` get the file from branch master
  - Put cursor on SHA and `<enter>` to navigate betwwen commits
