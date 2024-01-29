

<h2>Description</h2>
Project consists of using linux command line to change user permissions for various files.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Linux command line</b>
- <b>File permissions</b>

<h4>Through Linux commands an analyst is able to change the permissions on each file. For example, In this scenario I have been asked by my company to change the permissions for access to files for several different groups and individuals in our organization. This project will use common commands such as “ls -la” to list all normal and hidden files and their file permissions as well as “chmod” to change the permissions of directories and files. </h4>
<br/>
<br/>

<h2>Program walk-through:</h2>


- Pwd (print working directory) to see what directory I am currently in
- Next, I list out all the directories and files in the “researcher2” directory by using the “ls” command
- I navigate to the “projects directory” by using the “cd” (change directory” command
- Lastly, I used the command “ls -la” to list out all normal and hidden files and directories and the permissions associated with each 
<br/> 
<br/>
<img src="https://i.imgur.com/ePCGcWs.png" height="80%" width="80%" alt="Vulnerability Scan Start"/>
<br />
<br />

The project.k file permissions string is in the screen shot below<br/>
<img src="https://i.imgur.com/0S2ueUr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- The first character in the permission string is a “-”, which indicates that it is a file, if it was a directory the first character would be a “d”
- The next three characters are r, w, and -. This indicates the user has read and write permission but not execute permissions.
- The next three characters are r, w, and -. This indicates the group  has read and write permission but not execute permissions.
- The next three characters are r, w, and -. This indicates the other group has read and write permission but not execute permissions.
<br />
<br />


Change permissions of project_k.txt file<br/>
<img src="https://i.imgur.com/ubWiqPn.png" height="80%" width="80%" alt="Vulnerability Scan searching"/>
- I use the chmod (change mode) command to change the permissions of the “project_k.txt” file. 
- O=r overwrites the “other” owner type privileges to be read-only
- I list the files and permissions with the ls -la command again to verify that “project_k.txt” has only read permissions for the “other” owner type, which it does as indicated by “r- -” to tend the permissions string. 



<br />
<br />

<br />
Change permissions of a hidden file <br/>
<img src="https://i.imgur.com/1cZVlbM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- I used the “ls” and “-la” command to listen normal and hidden files and their permissions string
- I changed the permissions on the hidden file .project_x.txt so that the user and group owner types could have read privileges by using the CHMOD g=r (this overwrites any old permissions to let group have read permissions) followed by u=r (this overwrites any old permissions to let user have read privileges)
- I then used the “ls” and -”la” commands to listen out the permissions for all files and directories in the projects directory and I verified that the hidden file .project_x.txt now had read permissions for the user and group.


Change permissions of the "drafts directory" <br/>
<img src="https://i.imgur.com/2N6AJuo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- I list the permissions in the projects directory and observe that the drafts directory string is “d r w x - - x - - -”

This string indicates that it is a directory, the user has read, write and execute permissions "r-w-x", the group has only execute permissions "- - x" and the other owner type has no permissions "- - -". 

However, only the user owner type should have any permissions at all.

-  I use the chmod g-x to remove execute permissions from the group owner type

- 	I use the ls -la command to verify that the group no longer has execute permissions 
              which is confirmed by the new string of “d r w x - - - - - -”



<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
