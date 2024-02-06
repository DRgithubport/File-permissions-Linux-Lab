

<h1>Linux File Permissions Lab</h1>


<h2>Description</h2>
This Linux file permissions project involves exploring and managing access controls for files and directories. As a security analyst, the task includes checking, modifying, and describing permissions using commands such as ls -l and chmod. The project aims to enhance understanding of access security, with a focus on identifying and addressing permission issues in a practical Linux environment.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Linux</b> 
  

<h2>Environments Used </h2>

- <b>Linux Command-Line

<h2>Lab walk-through:</h2>

<p align="center">
<h3>Check file and directory details:</h3>
<p align="left">
The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system.
<br />
<img src="https://github.com/DRgithubport/File-permissions-Linux-Lab/blob/afcb32399510febf465aefe1700552a39a6e2868/first%20pic%20.jpg" height="80%" width="80%" />
<br />
<br />
The first line of the screenshot displays the command I entered, and the other lines display the output. The code lists all contents of the projects directory. I used the ls command with the -la option to display a detailed listing of the file contents that also returned hidden files. The output of my command indicates that there is one directory named drafts, one hidden file named .project_x.txt, and five other project files. The 10-character string in the first column represents the permissions set on each file or directory.
<br />
<h3>Describe the permissions string</h3>
The 10-character string can be deconstructed to determine who is authorized to access the file and their specific permissions. The characters and what they represent are as follows:<br />
  <br />
●	1st character: This character is either a d or hyphen (-) and indicates the file type. If it’s a d, it’s a directory. If it’s a hyphen (-), it’s a regular file.<br />
  <br />
●	2nd-4th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the user. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted to the user.<br />
<br />
●	5th-7th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the group. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted for the group.
<br />
<br />
●	8th-10th characters: These characters indicate the read (r), write (w), and execute (x) permissions for other. This owner type consists of all other users on the system apart from the user and the group. When one of these characters is a hyphen (-) instead, that indicates that this permission is not granted for other.
<br />
<br />
For example, the file permissions for project_t.txt are -rw-rw-r--. Since the first character is a hyphen (-), this indicates that project_t.txt is a file, not a directory. The second, fifth, and eighth characters are all r, which indicates that user, group, and other all have read permissions. The third and sixth characters are w, which indicates that only the user and group have write permissions. No one has execute permissions for project_t.txt.
<br />
<br />
<h3>Change file permissions:</h3> 
  The organization determined that other shouldn't have write access to any of their files. To comply with this, I referred to the file permissions that I previously returned. I determined project_k.txt must have the write access removed for other.
  <br />
  <br />
The following code demonstrates how I used Linux commands to do this:
<br />
<img src="https://github.com/DRgithubport/File-permissions-Linux-Lab/blob/27c6144c7077414ff8bc9d3806116d20c14626ad/2nd%20pic.png" height="80%" width="80%"/> <br />
<br />
The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. The chmod command changes the permissions on files and directories. The first argument indicates what permissions should be changed, and the second argument specifies the file or directory. In this example, I removed write permissions from other for the project_k.txt file. After this, I used ls -la to review the updates I made.
<br />
<br />
<h3>Change file permissions on a hidden file:</h3> 

The research team at my organization recently archived project_x.txt. They do not want anyone to have write access to this project, but the user and group should have read access.<br />
<br />
The following code demonstrates how I used Linux commands to change the permissions:<br />
<img src="https://github.com/DRgithubport/File-permissions-Linux-Lab/blob/cb5ae4c52971aaa7658ee1267cc1aec06cb31350/3rd%20pic.png" height="80%" width="80%"/> <br />

The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I know .project_x.txt is a hidden file because it starts with a period (.). In this example, I removed write permissions from the user and group, and added read permissions to the group. I removed write permissions from the user with u-w. Then, I removed write permissions from the group with g-w, and added read permissions to the group with g+r.
<br />

<h3>Change directory permissions:<h3/> 

<h4>My organization only wants the researcher2 user to have access to the drafts directory and its contents. This means that no one other than researcher2 should have execute permissions.<br /><h4/>

<br />
The following code demonstrates how I used Linux commands to change the permissions:<br />
<img src="https://github.com/DRgithubport/File-permissions-Linux-Lab/blob/f6ca1fc0776a511a4cdfbb23226a2215c87b47fb/4th%20pic.png" height="80%" width="80%"/> <br />
<br />
The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I previously determined that the group had execute permissions, so I used the chmod command to remove them. The researcher2 user already had execute permissions, so they did not need to be added.<br />
<br />
<h3>Summary</h3>
I changed multiple permissions to match the level of authorization my organization wanted for files and directories in the projects directory. The first step in this was using ls -la to check the permissions for the directory. This informed my decisions in the following steps. I then used the chmod command multiple times to change the permissions on files and directories.


