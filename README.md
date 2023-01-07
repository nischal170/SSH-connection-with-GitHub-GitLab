# SSH-connection-with-GitHub-GitLab
Using GitHub or any git hosting services  with SSH (Secure Shell)
Steps for ssh key in git .

 1. Generate ssh key using the below command in command prompt(if you have windows PC)
	
	 1. ssh-keygen -t rsa -b 2048 -C "Your Email"
			rsa is encryption algorithm,you can use other encryption like "ed25519" also.
		Your email refers to your sign in email for that git service
			example:
				 - "nischal.neupane@gitlab.com" for my gitlab
				- "nischalneupane17@gmail.com" for my github account
	2. give file a name, like "forGitHub".
	3. two files will be generated inside c:\users\<your Name>\
				like 
				
				1. forGitHub==>This is private key,keep this safe.
			
				2. forGitHub.pub==>This is the file we require.(It contains the key which you have to paste in Github/Gitlab)

	4. make a folder named".ssh" inside "c:\users\<your Name>\

2. Add the key to ssh-agent.
	- start the ssh-agent in the background
		paste this in git bash ==>  $ eval "$(ssh-agent -s)"
	- Add your SSH private key to the ssh-agent
		open git bash in "c:\users\<your Name>\" and paste this
		ssh-add ~/.ssh/forGitHub
			
		.ssh is the name of the folder,
		forGithub is the name of the file

3. Add the ssh key obtained  from file in step (1.iii.2) in github/gitlab in preferences>SSH setting

4.Test the connection
	

> ssh -T git@github.com


	you'll see something like 

>Hi USERNAME! You've successfully authenticated...






