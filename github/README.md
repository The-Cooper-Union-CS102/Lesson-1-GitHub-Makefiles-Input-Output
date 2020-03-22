# Introduction to Git and GitHub

Git is a version control system that can be used to keep track of the entire
history of your software projects.  It is an industry standard and a using it
is a very useful skill to have.  

GitHub is a website that "hosts" your Git project.  That means you can upload
your project here which serves as a backup and allows you to share it with
others.

All homework assignments for this course will be submitted through GitHub,
so it is very important that you learn the basics.

## Envrionment Setup

First make an account at `https://github.com/`.  I advise you to choose a
professional name as GitHub profiles are often shared on resumes.

Git should already be installed on your terminal of choice by default.  If it
is not, see me and I will help you get it installed.

In order to connect your terminal to GitHub, you must run the following in your
terminal:

```bash
git config --global user.name "Your Name"
git config --global user.email "yourEmail@cooper.edu"

cd ~
mkdir -p .ssh
ssh-keygen -C "yourEmail@cooper.edu" -t rsa -f .ssh/id_rsa -N ""

cat .ssh/id_rsa.pub
```

Now in GitHub, click your icon in the top right, then `settings` then
`SSH and GPG keys` then `New SSH key`, paste the result from the previous
command in the box, and click `Add SSH Key`.

You can find more information [here](https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)

## Creating a new repository

A respository is a collection of code in Git or GitHub.

Create a new respository by going to `https://github.com/` and clicking `New`
in the upper left of the screen.  Type `hello-world` for the name and make sure
to check the box that says `Initialize this repository with a README`, then
click `Create Repository`.  Now, click `SSH` and copy the URL to the right of
it.  In your terminal, running the command `git clone {URL}` should produce a
new directory with your repository inside.

## Creating a new Branch

Now `cd` into the newly created repository.  You can create a new branch by
running `git branch newBranch`.  In order to start modifying this branch, you
must also run `git checkout newBranch`.  A shorthand that combines both of
these commands is `git checkout -b newBranch`.

## Modifying content

Modifying a file takes a couple steps.  These steps may feel unintuitive and
confusing, but they will become second nature as you gain experience.

First, to view your status at any time, type `git status`

You can append to `README.md` by running the command 
`echo "first modification" >> README.md`.  Run `git status` after to see what
has changed.  Now run `git add README.md` and run `git status` again.  Finally,
run `git commit -m 'first commit'` and `git status` one more time.  Finally,
upload your change to GitHub with `git push origin newBranch`.  This is
a very common workflow which makes a change, adds the change to the "staging
area", commits the change to your local repository, and pushes the change
to GitHub (the remote repository).

If you remember:
* `add`
* `commit`
* `push`

You can do most of what you need to do.

## Pull Requests

If you go back to your repository on GitHub, you (hopefully) not see any
changes in `README.md`.  However, you may see a notification with a button
that says `Compare & pull request`, and if you click the button that says
`Branch: master` you should see the new branch you created.

Navigate into the `Pull requests` tab and click `New pull request`.  The first
branch is the one you are pulling into, the second is the one that has
modifications.  Select the second branch and choose the new branch you created.
You will see any differences highlighted here.  Click `Create pull request`.
Do NOT click `Merge pull request` yet.

## GitHub Classrooms

You join the classroom with [this link](https://classroom.github.com/classrooms/62485055-the-cooper-union-cs102)

Finish the [first assignment](https://classroom.github.com/a/xNJwXTU2) as fast
as possible so I know you are able to connect.

You may push all your changes directly to the `master` branch if you wish.
I will leave you feedback on the automatically created pull request to the
`feedback` branch.  Automated tests will also be run which will tell you if 
your output is correct.  Please do not merge this pull request.
