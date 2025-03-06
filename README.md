Vim_tips 
------------------------------------------

- Using VIM effectively can be incredibly helpful when preparing for and passing Kubernetes certification exams, such as the CKA (Certified Kubernetes Administrator) or CKAD (Certified Kubernetes Application Developer). These exams are hands-on and time-sensitive, so efficiency in editing and managing YAML files—a core task in Kubernetes—is crucial.

- [X] **To check VIM installed**
  ```bash
    -v vim
  ```
- [X] **To check default editor**
  ```Bash
    $ echo $EDITOR
    Or
    Env | grep Editor
  ```
- [X] **To change default editor**                                                                                     
    1) select-editor ( only if select editor package installed)
    2) ```sudo update-alternatives --set editor /usr/bin/vim.basic```   
       ```sudo update-alternatives --set vi /usr/bin/vim.basic```
    3) ```sudo update-alternatives --config editor```
    4) Add the following to your shell configuration (probably ~/.bashrc):
          export VISUAL=vim
          export EDITOR="$VISUAL"

 * **Entry && Exit commands**
     *  `i`   - insert mode to enter txt
     -  `Esc` - normal mode
     -  `:`   - command mode
     -  `:w`  - write the file but no quit
     -  `:q`  - to quit or exit if no changes are done
     -  `:q!` - exit without saving the file
     -  `:qa!`- exit and abort changes
     -  `:wq` - to write and quit
     -  `W 'filename-here'`  - to write and save with a name
     -  `X`   - write and exit
     -  `ZZ`  - save and exit quickly
     -  `ctrl+o` - to chnage to normal mode but stay in normal mode
     -  `:! 'Enter linux command here'`  - run linux command from VIM editor
    
* **Perform deletion**
     -  `di`  - delete everything inside the quotes
     -  `dG`  - delete content from cursor to end of file
     -  `dgg` - to delete everything from bootm to top line
     -   `x` - to delete a character
     -   `dd`- to delete current line

          -  _To delete in insert mode_:
             -  `ctrl+w` - to delet entire previous word
             -  `ctrl+h` - to delete one letter
             -  `ctrl+u` - to delet everything infront of the cursor
        
 
* **To set numbers for all files permanently**
      >Vim . Vimrc then add `set number`
    -  `: set number`   - to get line numbers for each line
    -  `:set nonumber`  - to take line numbers away 

  - To swap two lines -ddp
                                                      
          u- undo the previous action    
          yi"- copy everything inside quotes
          p - to paste that was copied
    
  - To indent
    insert mode S- to indent
    to indent entire document
    gg- got o first line
    gg=G to indent everything from top line to bottom
    - cmd mode: shift+v to select the txt****
          -Then shift+> to move those slectwd txt to right
          -Press ‘Y’ copy the selected txt
          -Go to insert mode then change to cmd mode to press ‘ p’
    ‘v’- to activate visual mode then use attows ro select lines or txt
     Visual mode ‘y’- copy or yank the txt or lines
    ‘p’- to put or paste the yanked txt
     Visual mode ‘: ‘<, ‘>sort ui - to sort lines in alphabetical order 

  - To move cursor
    L- cursor placed at low
    H-cursor placed at high
    M- cursor placed at middle
    ctrl+u- cursor up
    ctrl+d- cursor down
    W- word
    e - end of word
    E- end of word but skips :
    B- go back to start
    b- back one step
    ‘$’- takes you to the end of first line. But it won’t be in insert mode
    0- to go to start of line
    ‘gg’ - to move the cursor the first line of the file
    ‘G or shift+g’ - to take cursor the end of file

to set spell
:set nospell || :set spell& || :set spell!

To get help
:help #keyhere || :h  #keyhere
to check in visual 
:h v_d (#tocheck what does d key does in visual mode)

- **To edit and undo chnages**
 ‘A’ - insert plus append at last of first line
 ‘u’ - to undo recent changes
 ‘p’ - to put back the deleted line
 ‘ hjkln’ - to use instead of arrows
 ‘/word’ - to search a word in yaml ***
 ‘%s/old-word/new-word/g - to replace a pld word with new word
          
Advanced commands:
Vim +20 file-name - to start cursor at line 20 of that file 
Vim -o file1 file 2 - from terminal it opens two files in split window
vim -O file1 file2- from terminal it opens int vertical split window 
‘: split another file name’ or’:sp file-name’- to open two files in one window horizontally 
‘:vsplit file-name’ or ‘:vs file-name’ - to open a file in vertical split window
‘Crtl++ ww ‘ - to move to next file in split window 
‘:r filename-here’ - To add content of another file into current file
‘:e file-name’ - to open another vim with existing another file name ( current file also there in buffer)
‘:enew’ - to open an empty file in buffer mode
‘:bn’ - to see the next file of the buffer
‘:bn’ - to see the previous buffer file
‘:bd’ - to delete the current buffer 
‘:badd file-name’ - creates a buffer with new file but still cursor satya on current file

task 1-take back up yaml file before editing
```
k run tip1 --image busybox --dry-run-client -o yaml >1.yaml
cp 1.yaml 1.yaml.b
```
tip2-search and replace a word
'/' to search and enter n to got o next search
SHIFT+cto enter the new word

toip3- Append text at the end
'/' to search then 
SHIFT+a to append to the serch word

topic 4-Deleted sometxt from the cursor till end
search then
SHIFT+d to deletes then x

topis 5- indent single line
'o' to insert empty line
SHIFT+. -to indent right then enter to keep inteding the soaces
SHIFT+, - to indent left then enter to keep inteding the spaces

topic 6-add online below or above
'o'- add one line below
SHIFT+o- add one line above

tip 7- indent block of text
1. SHIFT+v
2. down and up arrows
3. SHIFT > or <
4. . (dot) [To repeat]

tip-8- Copy paste block of text
1.SHIFT+v
2.down+up arrow
3.y
4.p
tip9- comment a line or deleta line
0i# - to comment a line
dd- yto delete a line
 tip 10- save and quit

 :X- sva eand quit


   













Linux pstree
Tcpdump
$Docker system df
