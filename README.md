# How To Connect GitHub To Your 42 Project As A Backup

This tutorial for 42 students explains how to backup your projects on GitHub. 

If you have a local repository for a project that you simultaneously want to push to the Vogsphere and your GitHub account as a backup or for access from home, here's how to do it:

## Setting Up Your GitHub Account
0. Create a GitHub account and connect it with your 42 machine by adding your SSH key to your account (the same SSH key that you used for connecting to the Vogsphere). 
- Create a GitHub account here: https://github.com/signup
- Here's how to add your SSH key to your account: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

## Connecting Your Local Repository With GitHub

Let's use the repo "libft" as an example:

1. Go to your local repository "libft" that is already connected to the Vogsphere in the Terminal
2. Check, if it is correctly connected to the Vogsphere:

```
git remote -v
```

It should output something like this:

origin	git@vogsphere.42vienna.com:vogsphere/intra-uuid-f9895b4d-8fbe-4e62-8d1a-08a586f54a12-4462508-frafal (fetch)
origin	git@vogsphere.42vienna.com:vogsphere/intra-uuid-f9895b4d-8fbe-4e62-8d1a-08a586f54a12-4462508-frafal (push)

3. Go to your GitHub account and create a new private repository called "libft"
4. At "Quick Setup" click "SSH" and copy the repository URL

Mine for example would look like this: git@github.com:francisrafal/libft.git

5. Go to your terminal and in your "libft" directory, create a new remote called "all" that will be connected both to Vogsphere and GitHUb
```
git remote set-url --add all <your GitHub repository URL, i.e. git@github.com:francisrafal/libft.git>
git remote set-url --add all <your Vogsphere repository URL, i.e. git@vogsphere.42vienna.com:vogsphere/intra-uuid-f9895b4d-8fbe-4e62-8d1a-08a586f54a12-4462508-frafal>

```

6. Check if you are successfully connected to both remotes.

```
git remote -v
```
This should now look similar to this:

all	git@vogsphere.42vienna.com:vogsphere/intra-uuid-f9895b4d-8fbe-4e62-8d1a-08a586f54a12-4462508-frafal (fetch)
all	git@vogsphere.42vienna.com:vogsphere/intra-uuid-f9895b4d-8fbe-4e62-8d1a-08a586f54a12-4462508-frafal (push)
all	git@github.com:francisrafal/libft.git (push)
origin	git@vogsphere.42vienna.com:vogsphere/intra-uuid-f9895b4d-8fbe-4e62-8d1a-08a586f54a12-4462508-frafal (fetch)
origin	git@vogsphere.42vienna.com:vogsphere/intra-uuid-f9895b4d-8fbe-4e62-8d1a-08a586f54a12-4462508-frafal (push)

7. You can now push to both remotes to backup your project and have access to it from home:

```
git push all
```

