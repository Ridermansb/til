# Shortcuts

 - `gv` Reselect last visual selection.


# Selecting columns with visual block mode

 > [Vimcast episodes][2]

 - `ctrl+v` enter visual block mode
 - `I` To enter insert mode and start edit

# Using the changelist and jumplist

 > - `g;`, `g,` Go back/forward lastest edit cursor (back/forward where the last cursor was edited)
 > - `:changes` List all changes on current file
 > - `ctrl+o` , `ctrl+i` Moving betwwen jumps
 > - `:jumps` List all jumps options

# Buffers

`:ls` List all buffers
`:bn` / `:bp` Move to the next/previous buffer
`:e!` Reload the file 
`:q!` Discard buffer

`set hidden` will altomatically hidden unsaved buffers

## Legend
 - `%a` Indicate the current buffer
 - `#` Indicate the alternative buffer, you can switch by using `ctrl + ^`
 - `+` Indicate that buffer was not saved
 - `#h` The `h` Indicated that is not loaded into window

# Refining search patterns with the command-line window

 > [Vimcast episodes][3]

 - `\v'.+'` The `\v` means very magic mode, no need scape characters (This is try to find `'`)
 - `q/` show window pattern 
 - `q:` show window command 
 - If you are not in window, press `ctrl+f` to go to window
 - `:%s` is the substitute command, with `:%s/<pattern>/<replacement>`. If you leave pattern `:s//<replace>` the vim will use last pattern
 - `%` indicate the entiry file 

# Whitespace preferences and filetypes

 > [Vimcast episodes][4]

 - `autocmd FileType javascript setlocal ts=4 sts=4 sw=4 noexpandtab` Run for javascript,  
 - `:set ft?` or `:set filetype?` to ask what's filetype is for current buffer


[1]: http://vimcasts.org/episodes/working-with-buffers/
[2]: http://vimcasts.org/episodes/selecting-columns-with-visual-block-mode/
[3]: http://vimcasts.org/episodes/refining-search-patterns-with-the-command-line-window/
[4]: http://vimcasts.org/episodes/whitespace-preferences-and-filetypes/
