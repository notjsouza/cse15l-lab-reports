# Lab Report 4 - Vim #
---

## Step 4 ##

![Lab4Step4](Lab4Step4.png)

`<up> <up> <enter>`

>_I had SSH in my history from when I was setting up the GitHub SSH Key, so I pressed `<up>` twice to find it in my history and then pressed `<enter>` to run it._

## Step 5 ##

![Lab4Step5](Lab4Step5.png)

`git clone <click> <crl v> <enter>`

>_For context, I have two monitors. I had the terminal on one screen and the forked repository on the other, so after I typed `git clone` I clicked the copy button next to the link, then pasted it into the terminal with `<ctrl v>` and ran with `<enter>`._

## Step 6 ##

![Lab4Step6](Lab4Step6.png)

```
cd lab7 <enter>
sh test.sh <enter>
```

>_First, I changed the directory to /lab7 with `cd lab7 <enter>`, then ran the tests on ListExamples.java with `sh test.sh <enter>`._

## Step 7 ##

![Lab4Step7](Lab4Step7.png)

```
vim L <tab> .java <enter>
<right> i <backspace> 2 <esc> :wq <enter>
```

>_To make the changes to fix ListExamples.java, I first opened the file in Vim. To do this, I typed `vim L <tab> .java <enter>`. The `vim` keyword tells the terminal to open the specified file in the Vim editor. Typing `L <tab>` autocompleted `L` to `ListExamples.java`, then `<enter>` ran the command. Once I opened ListExamples.java in the Vim editor, the cursor was right next to the line I needed to change. This made it easy to just move one spot to the right with `<right>`, then change into insert mode with `i`. Once this was done, I deleted the `1` that was in the file and replaced it with `2`. After making the change, I exited insert mode with `<esc>` then saved and quit the editor with `:wq <enter>`.

## Step 8 ##

![Lab4Step8](Lab4Step8.png)

`sh test.sh <enter>`

>_I double-checked that this change in the Vim editor fixed the error by running `sh test.sh <enter>` again, and saw that all the test cases now passed._

## Step 9 ##

![Lab4Step9](Lab4Step9.png)

```
git add L <tab> <enter>
git commit -m Fixed 'L <tab> <enter>
git push <enter>
```

>_Lastly, I added the changed file to the commit queue with `git add L <tab> <enter>`, where `L <tab>` autocompleted to `ListExamples.java`. Next, I used `git commit -m Fixed 'L <tab> <enter>`, where `L <tab>` autocompleted to `ListExamples.java`, to commit the queued changes with a message 'Fixed'. The changes are pushed to the GitHub repository using `git push <enter>`._
