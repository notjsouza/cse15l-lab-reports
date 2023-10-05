## For each of the commands cd, ls, and cat, and using the workspace you created in this lab:
---
**No Args:**
1. ```
   [user@sahara ~/lecture1]$ cd
   ```
2. _I ran this from /home._
3. _There is no output here because I'm not specifying any location to cd into. This command needs a destination, or nothing will happen._
4. _This is an error, cd is supposed to change the active directory. It isn't because I'm not giving any new location to change to._ <br />

<br />

1. ```
   [user@sahara ~]$ ls
   lecture1
   ```
2. _I ran this from /home._
3. _The output shows all the files available in this directory._
4. _There is no error in this output. It displays all the files currently accessible from the working directory._ <br />

<br />

1. ```
   [user@sahara ~]$ cat
   ```
2. _I ran this from /home._
3. _There is no output because cat takes a file and prints it to the terminal. Because no file was specified, there was no output and I needed to end the task with CTRL + C._
4. _This is an error because cat requires a file to read from to work properly._

<br />

---
**With Path to Directory:**

1. ```
   [user@sahara ~]$ cd /home/lecture1
   [user@sahara ~/lecture1]$
   ```
2. _I ran this from /home._
3. _The output changed the working directory from /home to /home/lecture1._
4. _This is not an error, I properly cd'd into the lecture1 file from /home._

<br />

1. ```
   [user@sahara ~]$ ls /home/lecture1
   Hello.class  Hello.java  messages  README
   ```
2. _I ran this from /home._
3. _The output showed all the files within the /home/lecture1 directory._
4. _There is no error, all the files are displaying properly from the correct directory._

<br />

1. ```
   [user@sahara ~]$ cat /home/lecture1
   cat: /home/lecture1: Is a directory
   ```
2. _I ran this from /home._
3. _The output printed the specified working directory and recognized it as a directory._
4. _This is an error because cat is supposed to print the contents of files, not label directories._

<br />

---
**With Path to File:**

1. ```
   [user@sahara ~/lecture1]$ cd Hello.java
   bash: cd: /home/lecture1/Hello.java: Not a directory
   ```
2. _I ran this from /home/lecture1._
3. _The output printed an error when I tried to cd into a file._
4. _This is an error, cd is supposed to be used to change the active directory to another directory, not a file._

<br />

1. ```
   [user@sahara ~/lecture1]$ ls Hello.java
   Hello.java
   ```
2. _I ran this from /home/lecture1._
3. _The output displayed 'Hello.java', which is the file that's being called._
4. _There is no error, Hello.java is the only file that can be printed by this command._
   
<br />

1. ```
   [user@sahara ~/lecture1]$ cat Hello.java
   import java.io.IOException;
   import java.nio.charset.StandardCharsets;
   import java.nio.file.Files;
   import java.nio.file.Path;
   
   public class Hello {
      public static void main(String[] args) throws IOException {
         String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);
         System.out.println(content);
      }
   }
   ```
2. _I ran this from /home/lecture1._
3. _The output has a printed version of the Hello.java class._
4. _There is no error, the file is properly printed to the console._
