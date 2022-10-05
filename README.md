# How To Connect GitHub To Your 42 Project As A Backup

This tutorial for 42 students explains how to automatically backup your projects on GitHub

If you have a local repository for a project that you simultaneously want to push to the Vogsphere and your GitHub account as a backup or for access from home, here's how to do it:

## Set Up Your GitHub Account
Create a GitHub account and connect it with your 42 machine by adding your SSH key to your account (the same SSH key that you used for connecting to the Vogsphere). 
- Create a GitHub account here: https://github.com/signup
- Here's how to add your SSH key to your account: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

## Connect Your Local Repository With GitHub

Let's use the local repo "libft" as an example:

1. Go to your local repository "libft" that is already connected to the Vogsphere in the Terminal
2. Check, if it is correctly connected to the Vogsphere:

```
git remote -v
```

It should output something like this:

```
origin	git@vogsphere.42vienna.com:vogsphere/intra-uuid-f9895b4d-8fbe-4e62-8d1a-08a586f54a12-4462508-frafal (fetch)
origin	git@vogsphere.42vienna.com:vogsphere/intra-uuid-f9895b4d-8fbe-4e62-8d1a-08a586f54a12-4462508-frafal (push)
```

3. Go to www.github.com/new and create a new private repository called "libft"
4. After creating the repository, at "Quick Setup" select "SSH" and copy the repository URL

Mine for example looks like this: `git@github.com:francisrafal/libft.git`

5. Go to your terminal and in your "libft" directory, create a new remote called "all" that will be connected both to Vogsphere and GitHub
```
git remote add all <your Vogsphere repository URL, i.e. git@vogsphere.42vienna.com:vogsphere/intra-uuid-f9895b4d-8fbe-4e62-8d1a-08a586f54a12-4462508-frafal>
git remote set-url --add all <your GitHub repository URL, i.e. git@github.com:francisrafal/libft.git>

```

6. Check if you are successfully connected to both remotes.

```
git remote -v
```
This should now look similar to this:

```
all	git@vogsphere.42vienna.com:vogsphere/intra-uuid-f9895b4d-8fbe-4e62-8d1a-08a586f54a12-4462508-frafal (fetch)
all	git@vogsphere.42vienna.com:vogsphere/intra-uuid-f9895b4d-8fbe-4e62-8d1a-08a586f54a12-4462508-frafal (push)
all	git@github.com:francisrafal/libft.git (push)
origin	git@vogsphere.42vienna.com:vogsphere/intra-uuid-f9895b4d-8fbe-4e62-8d1a-08a586f54a12-4462508-frafal (fetch)
origin	git@vogsphere.42vienna.com:vogsphere/intra-uuid-f9895b4d-8fbe-4e62-8d1a-08a586f54a12-4462508-frafal (push)
```

7. You can now always push to both remotes to backup your project and have access to it from home:

```
git push all
```
## Questions?

Write me on Discord: Francis Rafal#1334

