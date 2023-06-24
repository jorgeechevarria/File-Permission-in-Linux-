<p align="center">
<img src="https://i.imgur.com/KrM1r7o.png" alt="linux logo"/>
</p>

<h1>Linux - File permissions</h1>
The research team at my organization needs to adjust the file permissions for specific files and directories within the projects directory. The current permissions don't align with the appropriate level of access that should be granted. By reviewing and modifying these permissions, we aim to enhance the security of our system. To accomplish this, I undertook the following steps:



<h2>Check file and directory details</h2>

In the section i used ( cd /home/researcher2/projects ) to get to the directory
And used ( l -l to be able to see the permissions )
<p>
<img src="https://i.imgur.com/hEbVvk6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<h2>Describing the permissions string</h2>

As you can see the directory and files have different permissions
A full permissions on directory would look like this
“ drwxrwxrwx “
If it starts with a ( d ) its a directory
If it starts with ( - ) its a file
R = read, w= write, x = execute this is what the permissions look like on a string.
“ drwxrwxrwx “ to break it down further in the string you have sections
It looks like this d-rwx-rwx-rwx
The first group of letters “rwx” is the “user “section, the second is the “ group”, and third is
“other”
d-rwx-rwx-rwx

<p>
<img src="https://i.imgur.com/2iLJMZA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Change file permissions</h2>

As you can see “project_k.txt “ have writing permissions that shouldn't be available in this case.
We will use the chmod command to change the permissions
[ chmod o-w project_k.txt ] and used [ ls -l ] to see the permissions and see the changes.

<p>
<img src="https://i.imgur.com/ZRKUdNi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Change file permissions on a hidden file</h2>

I wanted to see if there were any hidden files so i used [ ls -a ] and [ .project_x.txt ] it's a hidden file. you can tell because it starts with a ( . )
To see the permission I used this command [ ls -l .project_x.txt ]
And I will change the permissions to ” r = read “ only [ chmod ug-w,g+r .project_x.txt ]

<p>
<img src="https://i.imgur.com/nlgCzeQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p>
<img src="https://i.imgur.com/u4umgCH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Change directory permissions</h2>

As you can see the directory in the group section is allowing to execute
We will use [ chmod g-x drafts ] to change the permission. And as you can see the x is no
longer there. Meaning there is no permission to execute.

<p>
<img src="https://i.imgur.com/OIci7Zm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Summary</h2>

Permissions in Linux are a critical aspect of maintaining security and controlling access to files and directories. They determine who can read, write, or execute files. Properly managing
permissions help prevent unauthorized access, data breaches, and unauthorized
modifications. It is essential to regularly review and set appropriate permissions to ensure the
confidentiality, integrity, and availability of sensitive information stored on Linux systems.
