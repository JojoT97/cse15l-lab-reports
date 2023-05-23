# Running Git Commands In Terminal

## Step 4:
```<up arrow> <enter>```
```(typed password) <enter> ```
The command I ran was ```ssh cs15lsp23lf@ieng6.ucsd.edu``` along with the password for my ssh account.
This allowed me to connect to the remote server.

<img width="537" alt="Screenshot 2023-05-22 211919" src="https://github.com/JojoT97/cse15l-lab-reports/assets/130265120/70f0a18f-8750-428b-a4ec-402d2ea39cb6">

## Step 5:
```<up arrow> <up arrow> <up arrow> <up arrow> <up arrow> <up arrow> <enter>``` 
the command I ran was the git clone command for my forked lab7 repository ```git clone https://github.com/JojoT97/lab7.git```.

<img width="464" alt="Screenshot 2023-05-22 212047" src="https://github.com/JojoT97/cse15l-lab-reports/assets/130265120/839f9e0f-6d96-4431-bcad-9e00ed995f25">

## Step 6:
```c d <space> l <tab>```
the keys typed above results in the command ```cd lab7/``` it changes the current directory to the lab7/ directory. I also use
the tab key for autocompleting certain parts of the command.

```<up arrow> <up arrow> <up arrow> <up arrow> <up arrow> <up arrow> <up arrow> <up arrow> <up arrow> <up arrow> <up arrow> <up arrow> <up arrow> <enter>```
the keys typed above results in the command ```javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java``` which compiles the test files.

```<up arrow> <up arrow> <up arrow> <up arrow> <up arrow> <up arrow> <up arrow> <up arrow> <up arrow> <up arrow> <enter>```
the keys typed above results in the command ```java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests``` which runs the test files. However the test files shows there are errors, so I will need to fix them.

<img width="527" alt="Screenshot 2023-05-22 212415" src="https://github.com/JojoT97/cse15l-lab-reports/assets/130265120/5023435d-2716-494c-bc07-cb020fc1c435">

## Step 7:
```l s <enter>```
the keys typed above results in the command ```ls``` which I use to list the files in the current directory, which is helpful for using commands on them.

```v i m <space> L i s t <tab> . j a <tab> <enter>```
the keys typed above results in the command ```vim ListExamples.java``` I make use of the tab key to autocomplete certain parts of the command.
What this command does, is allow me to edit the ListExamples.java file so I can fix the issue.

```i <esc> <:> <wq> <enter>```
I use the command I to enter insert mode an edit and fix the file. Then I use the esc key to exit insert mode, then the rest of the keys typed above results in the command ```:wq```.
the ```:wq``` command is a combination of the ```:w``` command and ```:q``` command, which means the ```:wq``` command both saves and quits the file currently being edited.

<img width="539" alt="Screenshot 2023-05-22 212947" src="https://github.com/JojoT97/cse15l-lab-reports/assets/130265120/a160afbb-f0ab-45ed-b53c-2d4c35fd003a">

## Step 8:
```j a v a c <space> L i s t <tab> . j a <tab> <enter>```
the keys typed above results in the command ```javac ListExamples.java``` I once again make use of the tab key to autocomplete certain parts of the command.
The above command is neccesesary in order to compile the ListExamples.java file so the changes i made can take effect.

```<up arrow> <up arrow> <up arrow> <up arrow> <enter>``` 
the keys typed above results in the command ```java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests``` which will run the 
test files once more, this time passing the tests.

<img width="536" alt="Screenshot 2023-05-22 213252" src="https://github.com/JojoT97/cse15l-lab-reports/assets/130265120/687528fb-c54f-4ee5-a2b6-8a26ca018dee">

## Step 9:
```g i t <space> a d d <space> L i s t <tab> . j a <tab> <enter>```
the keys typed above results in the command ```git add ListExamples.java```. This command tells git which files I want to commit.

```<up arrow> <left arrow> <left arrow> <left arrow> <left arrow> <left arrow> <left arrow> <left arrow> <left arrow> <left arrow> <left arrow> <left arrow> <left arrow> <left arrow> <left arrow> <left arrow> <left arrow> <left arrow> <left arrow> <left arrow> <backspacex3> c o m m i t <enter>``` Here I make use of the previously used git add command, except I use the left arrow key and backspace keys multiple times so I can remove the ```add``` part of the command, typing instead ```commit```. The final command is ```git commit``` which tells git to commit the ListExamples.java file I added. Git then brings up a prompt where I can add a commit message. I typed and used the ```i``` command to enter insert mode and added the message "fixed a file" than I typed:
```<esc>``` 
```:wq <enter>```
the ```esc``` key exited enter mode, the ```:``` command allowed me to enter the ```wq``` command which both saved and quit the readme file I typed the message in.

Finally i typed ```g i t <space> p u s h <space> g i t @ g i t h u b . c o m : J o j o T 9 7 / l a b 7 . g i t <enter>```
which pushed the changes i committed to the forked github repository.

<img width="632" alt="Screenshot 2023-05-22 224524" src="https://github.com/JojoT97/cse15l-lab-reports/assets/130265120/d1c14cac-dc2b-494b-baac-156b854e8098">
