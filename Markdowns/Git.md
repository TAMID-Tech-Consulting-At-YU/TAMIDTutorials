# Git Installation

If this is your first time using git, please create an account here, then follow the download instructions. For those not new to git, you can skip the "Creating your first repository" section and clone the current one if you want to use any of the demo code I wrote. If you are new to git, I would recommend getting used to setting up a repository.

#### Don't get frustrated if things don't go as planned. Using git can be confusing. In my first semester, I had to re-clone my class git three times.

# Windows
## Downloading
Begin by going to the official [Git website](https://git-scm.com/downloads) and choosing the windows option. Then follow the recommended setup, and you shouldn't have to change anything. 

## Confirming

Press the windows button or navigate to the search bar and type ```Git Bash``` which should display the app that opens a bash terminal. 

# MacOS

### Downloading
I recommend using [Homebrew](https://brew.sh/) which a package manager for macOS

Open a terminal and run:

```
brew install git
```

### Confirming
Confirm by running 
```
git --version
```

# Creating your first repository

### Creating the repo
Go to the [github website](https://github.com/) and press "Start a project" choose a repo name like "MyFirstRepo"; then add a README.md because they are good practice to have when explaining your project and how to download/use it.

### Creating the local repo folder 

Create a new directory for your first repo by opening a regular command line and running:

```
mkdir git_test
```

```
cd git_test
```

You may have to configure your local git credentials to access your GitHub by running:

```
git config --global user.name "github_username"

git config --global user.email "email_address"
```

### Cloning MyFirstRepo

To clone your GitHub repo navigate to the repositories website, and there will be a button called "code" which will give you an HTTPS URL to copy, then run in your ```git_test``` folder:

```
git clone repository_url
```

Now navigate to the repo by 
```
cd MyFirstRepo
```

Congradulations! Thats your first repo!!

## Git Commands
Create a text file or a hello world project in your favorite language. 

To check untracked files on your local machine that are not on your GitHub yet run:
```
git status
```
Add your new file to get it ready to be committed to the repo by running: 
```
git add new_file
```
Then run ```git status``` one more time to see that it is staged to commit.

To commit that file with a useful comment about what you're adding or changing run:

```
git commit -m "Comment about the new file or changes made in an existing file"
```

Finally, push the file to your repo.

```
git push
```

It may ask you for your username and password again.

Everytime you change anything in that file, the file will become untracked, and youll have to ```add```, ```commit```, and ```push``` to update it.

### I may add more advanced git commands later, but I recommend reading about git and getting used to using it.

[Tutorial Source](https://phoenixnap.com/kb/how-to-install-git-windows) 
