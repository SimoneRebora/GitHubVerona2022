# Basic commands to use Git

## 0. Open a command line tool
- **Terminal** for Mac and Linux
- **Git BASH** for Windows (should have been installed together with Git)

## 1. Browse your computer

First, you need to be able to browse your computer, in order to find the folder you want to work with.  
1. To see where you are, you can use the command `pwd` (that reads: "print working directory")
2. To see the files/folders that are stored where you are, use `ls`
3. To move to another folder, use `cd my_folder`

### 1.1 Example

In a situation like the following:

![Screenshot from 2022-01-06 11-55-17](https://user-images.githubusercontent.com/29945305/148372437-790c25a1-b80f-46ef-837f-f15c808b8518.png)

To move from your location ("my_folder") to "my_other_folder", you need to write:

`cd my_other_folder`

You can verify that you actually moved there by writing:

`pwd`

Then, if you want to go back to the previous folder ("my_folder"), you need to write:

`cd ..`

...where the two dots mean the father (above) folder

## 2. Clone a repository

If you want to clone a repository by somebody else (or that you have created), you need to use the command: `git clone repository_url`

### 2.1 Example

If you want to clone **this** GitHub repository, you need to write:

`git clone https://github.com/SimoneRebora/GitHubVerona2022.git`

Note that the full url appears in the repository home page, top right, by clicking on the "code" button:
![Screenshot 2022-01-06 at 11-47-31 SimoneRebora GitHubVerona2022 Introduction to GitHub for the DH team at the University of](https://user-images.githubusercontent.com/29945305/148371256-cfc63acb-0c60-49ea-bc36-6220bf09ddca.png)

## 3. Update a repository

If the repository has changed after you cloned it (i.e. the maintainer has updated some files), you can upddate it by:
1. Moving the the main folder of your repository (using the `cd` command)
2. Writing the command `git pull`

### 3.1 Example

If you cloned **this** GitHub repository and you want to update it, you need to write:  
`cd GitHubVerona2022`  
`git pull`

## 4. Push a repository

If **you** changed the repository files on your computer and you want to commit your local changes to the online GitHub repository, you need to follow a more complex procedure.

### 4.0 Security set ups
These are setups you will need to do just once!

#### 4.0.1 Create a token
Before doing any commit from your computer, you need to create a personal access token (this is for security reasons).
1. Click on "Settings" in your personal profile
![Screenshot 2022-01-06 at 12-03-16 SimoneRebora - Overview](https://user-images.githubusercontent.com/29945305/148373395-339aab43-a843-416d-9ba1-19242b2afc79.png)
2. On the left, scroll down to click on "Developer settings"
3. Then click on "Personal access tokens"
4. "Generate new token"

...then you will have to select expiration date, scope (for basic usage, please select just "repo", i.e. "Full control of private repositories") and "Generate token"!  
![Screenshot 2022-01-06 at 12-24-27 Build software better, together](https://user-images.githubusercontent.com/29945305/148375773-4ee1ef5b-3bc5-439c-b943-a4f77907509c.png)

Please note that you will see the token just once, so copy/paste it immediately in your computer!  
Also remember that if you set an expiration date for the token, you will have to create another one once it has expired.

#### 4.0.2 Configure your identity in your computer
You will also need to set up your identity in your computer.  
This is good practice, because if you don't do it, the risk is that your pushes won't be assigned to you.  

Go to the Terminal (or Git BASH).  
Then call the following commands:
1. git config --global user.name "my_github_username"
2. git config --global user.email "my_github_email"

Of course, you will have to substitute "my_github_username" and "my_github_email" with your actual GitHub username and email.

### 4.1 Push changes
Go to the Terminal (or Git BASH).  
First of all, please make sure that you are in the main repository folder!!  
Then, you will need to use three commands, one after the other:
1. `git add -A` (this looks for all the changes in files - also deletions!) 
2. `git commit -m "my message"` (this commits the changes with a description message)
3. `git push origin main` (this pushes the changes to the "main" - or any other - branch)

You will be asked for your username and token. Then the push will be done!

### 4.2 Example
If I made changes to the files in this repository:
![Screenshot from 2022-01-06 12-21-59](https://user-images.githubusercontent.com/29945305/148375660-e33b777b-4a61-428a-b745-6d4d43ee7c26.png)

### 4.3 Tip
To make your next pushes faster, you can:
1. call the three commands in one line `git add -A; git commit -m "another message"; git push origin main`
2. some machines won't memorize the token. One way to do it, is to call the command `git config --global credential.helper cache` (which will save username/token to the cache)
