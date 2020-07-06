# Blamer

vim plugin script to easily tell someone who last updated the current line on your vim buffer.

## how to use

First you need python3 installed. Open the shebang part (line 1) of blame script and make sure
the python call part matches that of your environment.

Secondly, locate this blamer script to anywhere you like:

```
/path/to/your/script/blamer
```

plus, configure your vimrc as follows:

```
:command! -nargs=0 Blamer :call Blamer()
function! Blamer()
  let result = system("/path/to/your/script" . "blamer " . @% . " " . line("."))
  echo result
endfunction
```

Then, in your vim buffer (on premise that your repo is git managed), once call
:Blamer macro you can tell who edited/created current line your cursor is on.
