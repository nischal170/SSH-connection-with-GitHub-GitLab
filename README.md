# SSH-connection-with-GitHub-GitLab
Connect Using GitHub or any git hosting services  with SSH (Secure Shell)
Steps for ssh key in git .

 1. Generate ssh key using the below command in command prompt(if you have windows PC)
	
	 - A. `ssh-keygen -t rsa -b 2048 -C "Your Email"`
			rsa is encryption algorithm,you can use other encryption like "ed25519" also.
		Your email refers to your sign in email for that git service.
			For Example
				 *"nischal.neupane@gitlab.com" for my gitlab* AND
				*"nischalneupane17@gmail.com" for my github account*
	- B. give file a name, like "forGitHub".
	- C. two files will be generated inside the directory c:\users\<your user account Name>\
				like 
				
				1. forGitHub==>This is private key,keep this safe.
			
				2. forGitHub.pub==>This is the file we require.(It contains the key which you have to paste in Github/Gitlab)

	- D. make a folder named".ssh" inside "c:\users\<your user account Name>\

2. Add the key to ssh-agent.
	- to start the ssh-agent in the background-open git bash
		paste this in git bash ==>  `$ eval "$(ssh-agent -s)"`
	- Add your SSH private key to the ssh-agent
		open git bash in "c:\users\<your user account Name>\" and paste this
		`ssh-add ~/.ssh/forGitHub`
			
		.ssh is the name of the folder,if you don't find the .ssh folder just create it,
		forGithub is the name of the file(copy the file obtained from 1.c.1 to .ssh folder)

3. Add the ssh key obtained  from file in step (1.C.2) in github/gitlab in preferences>SSH setting

4.Test the connection
	

> `ssh -T git@github.com`


	you'll see something like 

>Hi USERNAME! You've successfully authenticated...






