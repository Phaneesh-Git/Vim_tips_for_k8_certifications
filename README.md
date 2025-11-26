![image](https://github.com/user-attachments/assets/158ecd7a-ab3e-4643-a87d-2f97ca47deee)



- Using VIM effectively can be incredibly helpful when preparing for and passing Kubernetes certification exams, such as the CKA (Certified Kubernetes Administrator) or CKAD (Certified Kubernetes Application Developer). These exams are hands-on and time-sensitive, so efficiency in editing and managing YAML files is a core task in these exams.

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
- [ ] **To get help with commands**

    - `:help #keyhere || :h  #keyhere` - to get hep related to keys

         - _To check in visual_
             * `:h v_d`-to check what does 'd' key does in visual mode

 * **Entry && Exit commands**
     *  `i`   - insert mode to enter txt
     -  `Esc` - normal mode
     -  `Esc+:`   - command mode
     -  `Esc+:w`  - write the file but no quit
     -  `Esc+:q`  - to quit or exit if no changes are done
     -  `Esc+:q!` - exit without saving the file
     -  `Esc+:qa!`- exit and abort changes
     -  `Esc+:wq` - to write and quit
     -  `Esc+:W 'filename-here'`  - to write and save with a name
     -  `Esc+:x`   - write and exit
     -  `Esc+ZZ`  - save and exit quickly (`:` not required)
     -  `ctrl+o` - to change to normal mode but stay in normal mode
     -  `Esc+:! 'Enter linux command here'`  - run linux command from VIM editor
    
* **Perform deletion**
     -  `ESc+di"`  - delete everything inside the quotes
     -  `Esc+da"'  - delete everything inside quotes and quotes
     -  `Esc+dG`  - delete content from cursor to end of file
     -  `Esc+dgg` - to delete everything from bottom to top line
     -   `Esc+x` - to delete a character
     -   `Esc+dd`- to delete the current line

          -  _To delete in insert mode_:
             -  `ctrl+w` - to delete entire previous word
             -  `ctrl+h` - to delete one previous letter or space
             -  `ctrl+u` - to delete everything infront of the cursor
        
 
* **To set numbers for all files permanently**
  >Vim . Vimrc then add `set number`
    -  `Esc+: set number`   - to get line numbers for each line
    -  `Esc+ :set nonumber`  - to take line numbers away 

  - `Esc+ddp` -To swap two lines, current with bottom line
  - `Esc+u`- undo the previous action    
  - `Esc+yi`- copy everything inside quotes
  - `insertmode+Ctrl+p` - to paste that was copied 
    
* **To indent lines**
  -   insert mode + `S`- to indent
      * _To indent entire document_
         * gg- go to first line then
            * gg=G to indent everything from top line to bottom
      * _To indent few lines of code_
          * cmd mode+`shift+v` to select the txt
          - Then `shift+>` to move the selected txt to right
          - Then `shift+<` to move those selected txt to left
 -   `v`- to activate visual mode then use arrows to select lines or txt
    then Visual mode+`y`- copy or yank the txt or lines
      -  `p`- to put or paste the yanked txt
-   Visual mode ‘: ‘<, ‘>sort ui - to sort lines in alphabetical order
-   ctrl-t, ctrl-d  - indent current line forward, backwards 
                  (insert mode)

- **To move cursor**
   - `Esc+L`- cursor placed at low
   - `Esc+H`-cursor placed at high
   - `Esc+M`- cursor placed at middle
   - `ctrl+u`- cursor up
   - `ctrl+d`- cursor down
   - `W`- word
   - `e` - end of word
   - `E`- end of word but skips :
   - `B`- go back to start
   - `b`- back one step
   - `$`- takes you to the end of first line. But it won’t be in insert mode
   - `0`- to go to start of line
   - `gg` - to move cursor to the first point of file
   - `G or shift+g` - to take cursor to the end of file

- **To set spell check**
    - `:set spell` - to check spell
    - `:set nospell || :set spell& || :set spell!`- to stop the spell check
      


- **To edit and undo chnages**
  - `A` - insert plus append at last of first line
   - `u` - to undo recent changes
  - `p` - to put back the deleted line
  - `hjkln` - to use instead of arrows
  - `/word` - to search a word in yaml
  - `%s/old-word/new-word/g` - to replace an old word with new word
          
## Advanced commands:
- `Vim +20 file-name` - to start cursor at line 20 of that file 
- `Vim -o file1 file 2` - from terminal it opens two files in split window
- `vim -O file1 file2`- from terminal it opens in vertical split window 
- `: split another file name` or `:sp file-name`- to open two files in one window horizontally 
- `:vsplit file-name` or `:vs file-name` - to open a file in vertical split window
- `Crtl++ ww` - to move to next file in split window 
- `:r filename-here` - To add content of another file into current file
- `:e file-name` - to open another vim with existing another file name ( current file also there in buffer)
- `:enew` - to open an empty file in buffer mode
- `:bn` - to see the next file of the buffer
- `:bn` - to see the previous buffer file
- `:bd` - to delete the current buffer 
- `:badd file-name` - creates a buffer with new file but still cursor stays on current file
- `:set paste` - **to keep the same indentation of copied script** 


✅ **_Task 1_** -take back up of a yaml file before editing
```
k run tip1 --image busybox --dry-run-client -o yaml >1.yaml
cp 1.yaml 1.yaml.b
```
✅ **_Task 2_** -search and replace a word
```
`/ word` to search and enter, `n` to got to next search word
`SHIFT+c`-to enter the new word
```

✅ **_Task 3_** - Append text at the end of a line
```
'/' to search then 
SHIFT+a to append to the search word
```

✅ **_Task 4_** -Delete some txt from the cursor till end

```
search '/word' then
SHIFT+d to delete then x
```

✅ **_Task 5_** - To indent a single line
```
'o' to insert empty line
SHIFT+. -to indent right then enter to keep intending the spaces
SHIFT+, - to indent left then enter to keep intending the spaces
```
✅ **_Task 6_** -Add a line below or above
```
'o'- add one line below
SHIFT+o- add one line above
```
✅ **_Task 7_** - To indent a block of text
```
1. SHIFT+v
2. down and up arrows
3. SHIFT > or <
4. . (dot) [To repeat]
```
✅ **_Task 8_** - Copy and paste a block of text
```
1.SHIFT+v
2.down+up arrow
3.y
4.p
```
✅ **_Task 9_** - comment a line or delete a line
```
0i# - to comment out a line
dd- to delete a line
```
✅ **_Task 10_**- save and quit
```x```

## 💻 Command Line Productivity Cheatsheet (Bash & Vim)

This reference sheet compiles essential keyboard shortcuts for efficient navigation, editing, and history management in the Linux/macOS terminal (Bash) and the Vim text editor.

---



### ⌨️ Bash Terminal Shortcuts (Readline)

These shortcuts are active when typing a command in your shell.

#### **Cursor Movement**

| Shortcut | Action |
| :--- | :--- |
| **Ctrl + A** | Move to the **beginning** of the line. |
| **Ctrl + E** | Move to the **end** of the line. |
| **Ctrl + B** | Move **backward** one character. |
| **Ctrl + F** | Move **forward** one character. |
| **Alt + B** | Move **backward** one **word**. |
| **Alt + F** | Move **forward** one **word**. |

#### **Editing & Deleting**

| Shortcut | Action |
| :--- | :--- |
| **Ctrl + U** | Delete everything **before** the cursor. |
| **Ctrl + K** | Delete everything **after** the cursor. |
| **Ctrl + W** | Delete the **previous word**. |
| **Ctrl + D** | Delete the character **under** the cursor. |
| **Ctrl + H** | Delete the character **before** the cursor (Backspace). |
| **Ctrl + L** | **Clear** the terminal screen. |

#### **Undo & Paste (Yank/Kill Buffer)**

| Shortcut | Action |
| :--- | :--- |
| **Ctrl + Y** | **Paste** (yank) the last deleted text (from the kill buffer). |
| **Ctrl + \_** | **Undo** the last editing action. |

#### **Scrolling & Searching History**

| Shortcut | Action |
| :--- | :--- |
| **Ctrl + R** | **Search** command history (interactive reverse-i-search). |
| **Ctrl + P** | **Previous** command in history. |
| **Ctrl + N** | **Next** command in history. |

---

### 🔎 Command History & File Search

#### **View & Reuse Previous Commands**

| Command/Action | Description |
| :--- | :--- |
| `history` | Display a list of previously executed commands. |
| `!!` | Run the **last** command executed. |
| `!123` | Execute command number 123 from history. |
| `!!:s/old/new/` | Run the last command, replacing the first occurrence of `old` with `new`. |
| `history \| grep keyword` | Search history for commands containing a specific `keyword`. |

#### **Clear Command History**

| Command/Action | Description |
| :--- | :--- |
| `history -d 123` | Remove command number 123 from history. |
| `history -c` | Clear all command history. |

#### **Finding Files**

| Command | Description |
| :--- | :--- |
| `find /path/to/search -name "filename" 2>/dev/null` | Find a file by name while **ignoring error messages** (`2>/dev/null`). |
| `locate filename 2>/dev/null` | **Faster** search for a file by name using a pre-built database. |

---

### 🗒️ Vim Editor Commands

These commands are used for editing and navigation within the Vim editor.

#### **Movement and Selection**

| Command | Mode | Action |
| :--- | :--- | :--- |
| **i** | Normal | **Insert** mode: Insert **before** the cursor. |
| **I** | Normal | **Insert** mode: Go and edit at the **beginning** of the line. |
| **A** | Normal | **Insert** mode: Go and edit at the **end** of the line. |
| **V** | Normal | Enter **Visual Line** mode (to select entire lines). |
| **d$** or **D** | Normal | **Delete** from the cursor to the end of the line. |

#### **Editing and Deleting**

| Command | Mode | Action |
| :--- | :--- | :--- |
| **dd** | Normal | **Delete** the current line. |
| **Ctrl + W** | Insert | Deletes the **previous word**. |
| **Ctrl + U** | Insert | Deletes everything **before** the cursor on the current line. |
| **Ctrl + H** | Insert | Deletes the character **before** the cursor. |
| **Ctrl + D** | Insert | Deletes the character **under** the cursor. |

#### **Indentation**

| Command | Mode | Action |
| :--- | :--- | :--- |
| **>** | Visual | **Indent** selected lines **right**. |
| **<** | Visual | **Indent** selected lines **left**. |

#### **Exiting**

| Command | Mode | Action |
| :--- | :--- | :--- |
| **ZZ** | Normal | **Save and exit** (equivalent to `:wq`). |

---




   














