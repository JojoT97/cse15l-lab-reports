# CSE15l Setup Tutorial

## Step 1, Install VScode:

[Visit this link](https://code.visualstudio.com/)
you should see a webpage that looks like this:
![Image](https://user-images.githubusercontent.com/130265120/230792166-7885167c-fda6-458c-9fb4-9c8074329ba3.png)

Select your operating system, press download and install.
After installing open the VScode application.

## Step 2, Remotely Connecting:

After having opened the VScode application, open a new terminal within VScode.
You can open a new terminal within VSCode by going to the top of the VScode window and select
Terminal > New Terminal. You can also use the shortcut Ctrl + Shift + `. Near the plus icon
in the terminal area, select the arrow. In the dropdown that apears select "Git Bash" as shown here:
![Image](https://user-images.githubusercontent.com/130265120/230792721-02fa8ee7-51ca-4bc4-812d-6da73c6e96d1.png)

Finally, to connect to a remote server type the following command in terminal: `sshcs15lsp23zz@ieng6.ucsd.edu`, replace (zz) with the letters from your course-specific account. Here is what terminal should look like after connecting to the remote server:
![Image](https://user-images.githubusercontent.com/130265120/233757114-87373762-fc70-44a6-bd86-bc406af0c063.png)


## Step 3, Trying Some Commands:

Now that you have connected to a remote server, lets try some commands.
Here are a list of useful commands you can try:

- cd ~
- cd
- ls -lat
- ls -a
- ls (directory) where (directory) is /home/linux/ieng6/cs15lsp23/cs15lsp23abc, where the abc is one of the other group members’ username
- cp /home/linux/ieng6/cs15lsp23/public/hello.txt ~/
- cat /home/linux/ieng6/cs15lsp23/public/hello.txt


Here is an example of me using a command:
![Image](https://user-images.githubusercontent.com/130265120/230793291-705cc05a-6bd2-4472-9dfb-a0403fbb5a19.png)
  
In this example, the cp command copies the borzoi2 image from my otherBorzoi folder to the parent borzois folder.

Here of examples of commands being used after connecting to a remote server:

The pwd command prints the working directory.
![Image](https://user-images.githubusercontent.com/130265120/233757913-c2647ca0-ed87-4121-b205-65b521a3c826.png)

The ls command lists everything in the working directory.
![Image](https://user-images.githubusercontent.com/130265120/233757976-5a360c9b-2679-4ccc-a599-2b2555c46333.png)

The cat command displays data from inside the given file. Since there is no data inside the file nothing was displayed.
![Image](https://user-images.githubusercontent.com/130265120/233758042-1b13d142-c256-4f31-9cdb-201589f27377.png)
