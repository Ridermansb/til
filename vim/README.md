# Using the changelist and jumplist

 - `g;`, `g,` Go back/forward lastest edit cursor (back/forward where the last cursor was edited)
 - `:changes` List all changes on current file
 - `ctrl+o` , `ctrl+i` Moving betwwen jumps
 - `:jumps` List all jumps options

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

[1]: http://vimcasts.org/episodes/working-with-buffers/
