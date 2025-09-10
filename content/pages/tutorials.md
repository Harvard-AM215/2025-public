Title: Tutorials
Slug: tutorials
Date: 2022-07-26
<!--
    vim: foldmethod=marker
-->

* [How to Setup your Private Class Repository](#tutorial-repo)
    * [Steps to Setup Your Private Class Repository](#tutorial-repo-steps)
    * [Add an SSH Key to Your Account](#tutorial-repo-ssh)
 * [Homework Workflow](#tutorial-hw)
    * [Example Homework Workflow](#tutorial-hw-example)
        * [Step 1: Branch Off](#tutorial-hw-example1)
        * [Step 2: Solving the Homework](#tutorial-hw-example2)
        * [Step 3: Create a Pull Request](#tutorial-hw-example3)
            * [Creating a Web Pull Request](#tutorial-hw-example3-webpr)
        * [Step 4: Submit on Gradescope](#tutorial-hw-example4) 

<!-- Private Repo {{{1 -->
## <a id="tutorial-repo"></a><a class="anchor-link" href="#tutorial-repo">How to Setup your Private Class Repository</a>

> All of your work in AM215 will be committed in your private class `git`
> repository hosted in the AM215 organization at
> <https://code.harvard.edu/AM215>. 
<!-- (The class project will be hosted in another
> repository in the same organization, see [Milestone
> 1]({filename}/project/milestone1/index.md) for this separate task.) -->

This tutorial walks you through the steps to create your private class
repository.  If you have already created `git` repositories on GitHub, then
there is nothing new to learn in this tutorial and you should be familiar with
the process already.

**A note on <https://code.harvard.edu/>:** this is an instance of a [GitHub
Enterprise](https://github.com/enterprise) edition hosted by Harvard University.
The user interface is identical to the public [GitHub](https://github.com/)
site.  The main difference is that <https://code.harvard.edu/> _is owned by
Harvard University_, whereas GitHub belongs to Microsoft which gives rise to
security concerns regarding data belonging to classes held at Harvard
University.

### <a id="tutorial-repo-steps"></a><a class="anchor-link" href="#tutorial-repo-steps">Steps to Setup Your Private Class Repository</a>

1. Obtain your Harvard
   [NetID](https://harvard.service-now.com/ithelp?id=kb_article&sys_id=507aca5a1b653700efd8a79b2d4bcb59)
2. Each day, in the afternoon, the members of the organization will be updated.
3. If the daily update happened and you cannot access the organization, please fill [this form](https://docs.google.com/forms/d/1TxncfkQD0EFG32qalEpsRYWcnoONKOfw6ThyAtsfmy0). You  must use our `*.harvard.edu` email.
4. Once added to the organization, navigate to <https://code.harvard.edu/AM215>
   (login if necessary) and click the green "New" button to add a new
   repository.
5. Your repository ***must be named after your NetID***.  You can add an
   optional description if you like.  Make sure the _private_ radio button is
   checked and click "Create repository".  You do not need to check any other
   options.

This is all you have to do for now.  In the first homework we will focus on how
to setup your new repository such that you can work with it from your laptop
(you can skip the landing page after you have created the repository). When you
navigate back to <https://code.harvard.edu/AM215> you should see something
similar to this:
![AM215 organization]({static}/pages/media/am215_org_initial.png)

* The `main_2025` repository is the main AM215 class repository which is used
  to distribute all of the class material during the semester. 
  In the first homework we will set this repository
  as an upstream such that you can conveniently unpack class material into your
  private repository.

> **Note:** private repositories are only visible to you within the
> organization.  Please do not create other repositories in the
> <https://code.harvard.edu/AM215> organization.  
>
>You have your own user account
> on <https://code.harvard.edu/> just like you have on GitHub or other
> providers.  Your user account requires your Harvard login credentials and is a
> good alternative to hosts like GitHub.  Feel free to create as many
> repositories in your user account as you like.

### <a id="tutorial-repo-ssh"></a><a class="anchor-link" href="#tutorial-repo-ssh">Add an SSH Key to Your Account</a>

In order to access content on <https://code.harvard.edu> using Git you need to
setup an [SSH](https://en.wikipedia.org/wiki/Secure_Shell) key.  Check if you
already have the file `~/.ssh/id_rsa.pub` (assuming RSA).  If you do not have
such a file you can create one with

```bash
ssh-keygen -t rsa -b 4096
```

Choose the default location by just hitting enter.  You may enter a password for
the key or just hit enter to go without password.  If go with password you will
have to enter it every time you use the key.  To upload the public key to your
Harvard [GitHub account](https://code.harvard.edu/), click on your icon in the
top right corner on your <https://code.harvard.edu> page, then click on
"Settings" and then "SSH and GPG keys" in the left panel. Alternatively use this
link <https://code.harvard.edu/settings/keys>. Click on the green "New SSH key"
button in the top right corner and give your new key a title (e.g. the name of
your laptop).  In the key field paste the contents of your *public key* found in
`~/.ssh/id_rsa.pub`.  Use for example

```bash
cat ~/.ssh/id_rsa.pub
```

and copy paste the output into the "Key" field on your GitHub page.  You are now
able to access any repositories on <https://code.harvard.edu> with corresponding
permissions. **Never share your *private key* `~/.ssh/id_rsa` with anybody.**

<!-- > **Note:** do not create a key in the class Docker container since the key will
> be lost when you exit the container.  For security reasons, sensitive keys
> like this should not be put in containers. -->


## <a id="tutorial-hw"></a><a class="anchor-link" href="#tutorial-hw">Homework Workflow</a>

The following are the basic rules we apply for homework submissions:

1. **Naming convention for homework directories:** your private repository
   should contain one `homework` directory on the repository root with `hwX`
   sub-directories for each homework assignment.  The `X` in `hwX` is to be
   replaced with the assignment number.  For example `hw1`, `hw2` and so on.
2. **Which files will be considered for grading:** within the sub-directory
   `hwX`, place the assignment files that you want us to grade in a directory
   called `submission`. _We will only grade data in these directories_.
3. **Pull request (PR):** your homework assignments must be completed on `git`
   branches called `hwX`, where `X` is again to be substituted with the
   assignment number.  _Your homework `X` submission requires an open pull
   request to merge the `hwX` branch into your `main` 
   branch for full points_ (both branches are inside your private class
   repository in the [AM215 organization](https://code.harvard.edu/AM215)). Some
   implications of this:
       + Solving homework on the `main` or `master` branch is always wrong.
       + For each homework submission you need to issue _one open_ PR.  _Merging
         an open PR **before** the teaching staff has reviewed and graded your
         work will make the PR disappear_.
       + Only files inside `submission` in PR `X` will contribute to your `hwX`
         grade (see next item).
4. **Gradescope:** your homework will be graded on the [Gradescope
   platform](https://canvas.harvard.edu/courses/108118/external_tools/89451?display=borderless)
   that has been setup and linked to the class canvas page.  The platform does
   currently not support submission directly via your Git repository.  You
   therefore have to create a `zip` archive of your `submission` directory
   created in step 2 above and upload the archive on
   [Gradescope](https://www.gradescope.com/courses/1112657).
   It is important that you zip-up the *directory* and not individual files
   inside.  You can use the command `zip -r submission.zip submission/`, where
   the `-r` option means add files *recursively*, `submission.zip` is the name
   of zip archive and `submission` is your homework submission directory from
   step 2 containing your solution.  This assumes you are in `homework/hwX`
   inside your Git repository.

_Points will be lost if any of these requirements are violated_.

> The teaching staff will review the open PR for each homework and grade your
> work accordingly.  Grades will be released on Canvas and feedback is provided
> through the Gradescope platform.  Once you have received the grade and
> feedback, your open PR for homework `X` can be merged into your `main` branch if there are no more pending issues. 
 After the PR is closed, you may delete the `hwX` branch in your repository.  This concludes a homework
> submission.


### <a id="tutorial-hw-example"></a><a class="anchor-link" href="#tutorial-hw-example">Example Homework Workflow</a>

This example is intended to help you internalize the three basic rules described
above. 
<!-- _Each homework awards 10 points by performing these steps correctly._ -->

> **Note:** Specific instructions provided in each homework assignment may
> override the following basic approach.

Suppose we want to work on homework assignment 3, which consists of 4 problems.

#### <a id="tutorial-hw-example1"></a><a class="anchor-link" href="#tutorial-hw-example1">Step 1: Branch Off</a>

The ease of _branching_ is the main strength of `git`.  Branches allow you to be
destructive without affecting production code or data.  The reason we solve
homeworks on individual branches is to help you develop a feel for this
protection and to materialize the required steps to create branches.  Branches
_will_ provide you true comfort when working on real projects outside of this
class.

1. Make sure your `main` branch is in the state you want your new
   branch to be based on.  If you need to synchronize with your default remote
   branch you can type

        git pull

2. The next step consists of creating and switching to a new branch that is
   based off the current branch.  For this you can use

        git checkout -b hw3
   which is how you did it before `git 2.23.0`.  Since the `checkout` command is
   [ambiguous](https://github.com/git/git/blob/master/Documentation/RelNotes/2.23.0.txt#L61), the preferred way for more recent versions of `git` is

        git switch -c hw3

You are now on a new branch called `hw3` as required.  You will need to issue a
pull request into `main` from this branch such that your homework
will be graded.  You can create the PR now (see below) or once you are done with
solving `hw3`, it does not matter to `git`.  (Pull requests are not something
designed by `git` itself, but rather by platforms like GitHub or GitLab.)

> **Note:** you will lose 5 points if you are not solving your `hwX` (in this
> example it is `hw3`) on a branch named `hwX`.  You are of course free to
> create additional branches besides `hwX` if suitable.


#### <a id="tutorial-hw-example2"></a><a class="anchor-link" href="#tutorial-hw-example2">Step 2: Solving the Homework</a>

The files the teaching staff will consider for grading have to be located in the
directory `homework/hw3/submission`.  You are free to put other files below
`homework/hw3` that might be useful when you revisit your work sometime later.
The problem sheet might be one of those files.  Class handouts are distributed
in the `main` [class repository](https://code.harvard.edu/AM215/main_2025).  You can
manually create these directories and copy the files you want into your `hw3`
directory using, for example:

        mkdir -p homework/hw3/submission
        cp <path to main class repo>/homework/hw3/hw3.pdf homework/hw3

Alternatively you can use `git` by configuring the `main` class repository as
another remote in your local `git` repository (see homework 1).  In this case
you can checkout all the distributed homework files at once with

        git checkout class/master -- homework/hw3

assuming that the remote points to <https://code.harvard.edu/AM215/main_2025> and is
locally named "`class`".  You may need to update your refs with `git fetch --all`
before you invoke the checkout command above.

The homework sheet will state what files have to be submitted.  For this `hw3`
we assume they are `P1.py`, `P2.py`, `P3.py` and `P4.py`, one for each of the
four problems.

> These files should run and return the required output.  They have to be
> submitted inside the `homework/hw3/submission` directory.

You should commit your work often in logical chunks.  Your commits are to be
done on the `hw3` branch, of course.  The following are a few commands that
might be helpful:

* Use `git status` often to check your local state.
* Use the `git add <file_name>` command to stage files you have changed for a
  commit.
* Use `git commit -m <commit message>` to create a commit with an appropriate
  commit message.
* Use `git stash` to temporarily stash modified files (similar to a commit but
  it is not written to the history).  Later on use `git stash list` to list all
  your stashed changes if you have used `git stash` multiple times.  You can
  check what will change when you apply the stash with `git stash show -p` and 
  apply the stashed changes with `git stash apply` (or
  `git stash pop` which also *removes* the stash from the list).  Note that
  these commands work on the first stash object in the list `stash@{0}` if you
  do not explicitly specify the stash object you want to apply.
* Use `git push` to push local branch/commits to your remote repository.
* Use `git restore <file_path>` to undo changes to a single file.
* Use `git revert <commit_SHA>` to undo the changes in a specific commit.

> Make sure you have committed your solution you want to submit inside the
> `homework/hw3/submission` directory with the required file names.


#### <a id="tutorial-hw-example3"></a><a class="anchor-link" href="#tutorial-hw-example3">Step 3: Create a Pull Request</a>

If you have local commits not pushed to the remote issue the `git push` command.
You are now ready to issue a pull request (you could also have done this step at
the very beginning of solving this homework, this is up to you).

The goal is to merge the `hw3` branch into your `main` branch
eventually.  The teaching staff must review and grade your work first, however.
There are two ways to accomplish a PR on GitHub:

1. Through the web browser at `https://code.harvard.edu/AM215/<your NetID>`.
2. Through the GitHub [command line client](https://cli.github.com/). This
   method is helpful if you get distracted from the context switch that is
   associated with the first method.

<!-- > **Note:** you will lose 2 points if you do not create a PR. -->

**Disclaimer:** you would not typically issue a PR for projects you are the sole
contributor. Pull requests are typical for large projects at a company in which
someone else will review your code before you can merge your code to the
production branch. We want you to become accustomed to this type of workflow. It
is a good idea to always use separate development branches. You should never
commit straight to your `main` or `master` branches until the changes have
thoroughly been tested.


##### <a id="tutorial-hw-example3-webpr"></a><a class="anchor-link" href="#tutorial-hw-example3-webpr">Creating a Web Pull Request</a>

1. Navigate to your `https://code.harvard.edu/AM215/<your NetID>` private class
   repository and click on the "Pull Requests" tab in the top left part of the
   window.
2. Click on the "New pull request" button
3. Choose your `main` or `master` branch as the _base_ (the one you want to
   merge into) and your `hw3` branch as the one you want to _compare_ to.
4. This should automatically reload the page and show the changes that will be
   applied.  Click on the "Create pull request" button.
   ![Create PR]({static}/pages/media/create_pr_am215.png)
5. You can optionally add comments to this pull request if you desire.  Click on
   the "Create pull request" button once more to create and _open_ the pull
   request.
6. The pull request is now open.  You can even push more commits to the `hw3`
   branch if you need to correct something (before the deadline has passed of
   course).  Therefore, you could also create the PR at the beginning of the
   homework.
   ![Open PR]({static}/pages/media/open_pr_am215.png)

> **Note:** DO NOT click on the button that says "Merge pull request" until
> you have received your grade and feedback for that homework.  You will lose 3
> points if you prematurely merge your PR.

#### <a id="tutorial-hw-example4"></a><a class="anchor-link" href="#tutorial-hw-example4">Step 4: Submit on Gradescope</a>

Your submission is now ready to be submitted for grading on
[Gradescope](https://www.gradescope.com/courses/NEW_COURSE_ID).
Simply create a `zip` archive of your `submission` directory you have created in
your Git repository, e.g. `submission.zip`, and upload it to Gradescope by
following the link above. You can use the command `zip -r submission.zip
submission/`, where the `-r` option means add files *recursively*,
`submission.zip` is the name of zip archive and `submission` is your homework
submission directory.

Since you track the change history of your work in
Git, you should not add `*.zip` files to your Git history.  You can simply
ignore such archives by adding the line
```
*.zip
```
to your `.gitignore` file in your repository root.
