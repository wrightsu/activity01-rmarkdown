Activity 1 - RMarkdown
================

It is assumed that you have watched the videos contained within
Preparation 1.

In this activity, you will:

-   Fork a GitHub repository.
-   Connect GitHub and RStudio and share files between these two tools
    (i.e., “clone” and “pull”).
-   Edit and view changes in narrative text and R code chunks in an
    RMarkdown document.
-   Create a branch within a GitHub repository.
-   Create and resolve a Pull Request between you and yourself.

## Version Control Overview

In this activity, we begin collaborating on coding projects with
ourselves. However, we can collaborate on projects with colleagues,
online acquaintances, **or**, simply, you and future you. Version
control is one way to keep track of what a person did and when, which is
much better than the system that I used through most of my studies:

![“Piled Higher and Deeper” by Jorge
Cham](http://phdcomics.com/comics/archive/phd101212s.gif)

The Google Workspace (Drive, Docs, etc.) is a spectacular tool where
people collaborate on many different types of projects. Google even has
a collaborating on coding notebooks (i.e., [Google
Colab](https://youtu.be/inN8seMm7UI)); however, it is lacking in some
programming language options. We can think of GitHub as a Google Drive
for collaborating on coding/software projects. Git would then be like
[Version History](https://support.google.com/docs/answer/190843?hl=en)
for a Google Doc.

Version control systems record the changes that are made each step of a
project. This allows you to rewind to start at a previous version and
play back through changes you made to eventually arrive at the most
recent version. Think back on what you did in your work for Preparation
1.

![Changes are saved sequentially](README-img/recording-changes.svg)

Each time you make a change, you can (and should), provide a brief,
informative **commit message**. A commit message is additional
information that can be used to help keep track of what changes were
made. There are many opinions on what needs to be included in commit
messages. My recommendation is to use active terms and be brief, but say
enough as to *why* this change was needed. Note that I do not always
follow this recommendation (I get lazy too), but future me really
appreciates it when current me is thoughtful 😄

### ☑️ Task 1: Fork This Repository

Recall from [Activity
0](https://github.com/gvsu-sta518/activity00-markdown#task-1-forking-the-repository)
that you made a personal copy of my repository to your GitHub area. If
you forgot how to do that, follow the directions in Task 1 except for
this activity - Activity 1.

<img src="README-img/noun_pause.png" alt="pause" width = "20"/>
<b>Planned Pause Point</b>: If you have any questions, contact Bradford
or another group.

<!--Recall Daniel from The Coding Train's video - he was working on a collaborative poem with different versions of himself.
I am going give a brief demonstration that *quickly* goes through:

1. Connecting RStudio and GitHub,
2. Creating a branch in GitHub and making and committing changes on this branch,
3. Creating a branch in RStudio and making and committing changes on this branch,
4. Merging these branches to the `main` branch in GitHub.

To see Daniel from The Coding Train work through a similar process on his collaborative poem, checkout:

[![Resolving Merge Conflicts](http://img.youtube.com/vi/JtIX3HJKwfo/0.jpg)](http://www.youtube.com/watch?v=JtIX3HJKwfo "1.9: Resolving Merge Conflicts - Git and GitHub for Poets")


<img src="README-img/noun_pause.png" alt="pause" width = "20"/> <b>Planned Pause Point</b>: If you have any questions, contact Bradford or another group.
-->

## Collaborating with No Conflicts

From your Preparation 1, you saw that if you (individually) made changes
to a branched version of your document, then merged those back into your
`main` branch, there were no issues with the merge. In fact, two people
could be editing the same file (on the same branch) and commit changes
with no issues occurring as long as the edits do not happen on the same
line.

![Different changes can be made, then
merged](README-img/collaborating-no-conflict.svg)

When resolving merge conflicts, we will be able to see each version of
the file (along with these changes and the files, useful metadata about
what changed, the complete history of committed changes make up a
repository). This allows us to decide which changes we want to keep for
the next version of the file. We can then keep these repositories in
sync across different computers to help facilitate collaboration among
different people (or versions of ourselves).

For the remainder of this activity, you will be working with your
neighbor(s). Remember to introduce yourself!

### Aside

I think it is too early to worry about merge conflicts as we are trying
to simply become familiar with GitHub. Therefore, we will circle back to
this after we update our STA 418/518 Workflow - focusing on
collaborating with current and future you. So far our workflow has been:

1.  Go to Bradford’s repository, and
2.  Fork a copy of Bradford’s repository into your GitHub space.

In a bit, we will see how to bring this repository into RStudio so that
we can edit and work with the R programming language!

### ☑️ Task 2: Exploring Files in GitHub

Before we get into updating our Workflow, let’s see what typical file
types look like in GitHub. There are a five versions of the same
document within the `docs/` directory/folder of this repo:

1.  `day1.md`,
2.  `day1.html`,
3.  `day1.docx`,
4.  `day1.pdf`, and
5.  `day1.Rmd`.

With your neighbor(s), explore how each file looks within your
repository (click on them to view them within GitHub). Discuss with your
neighbor(s) what is easily viewable and what is not. Keep this in mind
as we progress through this semester. That is, what do you need to
include so that people can view your work as you intended?

Jenny Bryan provides some great information on [repo
browsability](https://happygitwithr.com/workflows-browsability.html).
Throughout this course, we will use my opinionated method of repo
organization.

<!--
Now onto some doing.
**Important**; take these next steps slowly and communicate with your neighbor(s).
When you run into an issue, get a hold of me or another group.

When people are collaborating, they will likely step on each other.
This can even happen if an individual person is working on files from their laptop and a school computer.
We will now force a conflict, then work to resolve overlapping changes.

When changes are made to the same line, we must decide which change we want to keep (or further edit them to implement both).

![Conflicting changes](README-img/collaborating-conflict.svg)

Have one group member serve as the repo "owner" and the other(s) will be a "collaborator".
The owner should grant the collaborator(s) access to their `<username>/activity0101-merge-conflicts` repo:

1. Click on ![settings icon](README-img/settings.png) **Settings** tab on the top menu,
2. On the settings page, click on **Manage access** on the left-hand toolbar,
3. Click on the green **Invite teams or people** button, search by your group members username, and select them.

The collaborator can accept this invitation by clicking on the link that was emailed to the account attached to GitHub or type the following in their browser.
Now, each group member should create their own branch within the owner's repo (name this your name or GitHub username).

In your personal branch, navigate to and open the `day1.md` file to edit this document.
Each person will make a similar change so we can resolve a merge conflict:

1. At the end of the text on line 7 (i.e., "and `.pdf`.") press Enter/Return twice so that your cursor is now on a blank line 9,
2. Type your name on this new line 9 - each member provides their first and last name (or pseudonym for those wanting to maintain some level of anonymity),
3. Provide a meaningful commit message (and more descriptive message if so desired) and commit your changes.

Now, each member will create a **Pull Request** to add these changes back to the `main` branch.

1. Click on ![merge icon](README-img/merge.png) **Pull requests** tab on the top menu,
2. On the pull requests page, click on the green **New pull request** button,
3. On the "Comparing changes" page in the gray area with the ![compare icon](README-img/compare.png) icon, you want the left-hand selection to be `base: main` and the right-hand selection to be the member's branch (to request that the `main` branch pulls in the member's branch),
4. The screen will refresh with a snapshot of the changes at the bottom. For the time being, simply click on the green **Create pull request** button,
5. Provide a meaningful commit message (and more descriptive message if so desired) and create your pull request.

You will be taken to another page, but for now go back to the repo's main page.
The owner will now make decisions with respect to how these changes should be pulled in.
The collaborators should help the owner through this process.

1. The owner should go back to the to the ![merge icon](README-img/merge.png) **Pull requests** tab on the top menu.
  All current pull requests will be listed near the bottom of the page.
  The owner should click on their pull request and accept the changes.
  There should be no issues.
2. The owner will do this for each of the remaining pull requests except there will be issues.
  As a team, decide what information to keep (remember that you can keep both like we did in our example), then complete the pull request.
3. You can choose to completely close the pull request or keep them viewable here.
  You can always view closed pull requests by toggling that filter.

Congratulations, you collaborated on a GitHub project!
As we progress through this semester, remember to take things slow and reach out when you run into problems.
Together, all things are possible.
If there is time at the end of class, we will do this with the other members being the repo "owner".
However, there will be a lot of opportunities to continue practicing this throughout the semester.
Note that to be able to collaborate (submit pull requests) to a GitHub project, users do not need to be contributors.
They can fork the repo, make edits, and submit a pull request.

Look through your `<owner>/activity0101-merge-conflicts` repo's commit history.
Remember from The Coding Train's videos that you can view the commit history via the ![Clock history](README-img/noun_clock_history.png) icon or **Network** graph in the ![line graph](README-img/noun_line_graph.png) **Insights** tab.

<img src="README-img/noun_pause.png" alt="pause" width = "20"/> <b>Planned Pause Point</b>: If you have any questions, contact Bradford or another group.
-->

## Updating our Workflow

When doing work on activities in this course, our Workflow is going to
be:

1.  Go to Bradford’s repository;
2.  Fork a copy of Bradford’s repository into your GitHub space;
3.  Clone your GitHub repository to your RStudio session;
4.  Do work in RStudio: save, stage, provide a commit message, commit,
    push; and
5.  Continue until done.

Before we can do this, we need to get RStudio and GitHub communicating.

### ☑️ Tasks 3: Configure Git in RStudio

1.  Login to the [RStudio Workbench](https://rstudio.gvsu.edu/) using
    your GVSU username and password,

2.  Verify that you are in an RStudio session (i.e., not the RStudio
    Workbench Sessions/Project screen).

    There are a couple of ways to configure Git in RStudio. For STA
    418/518, we will use `{usethis}`.

    Note that when you see something like `{thing}` in my documents, I
    mean,“the R package called `thing`.”

    We will use the `edit_git_config` function from `{usethis}`.
    Throughout the semester, I will shorten this to be
    `usethis::edit_git_config` or, “from the R package `usethis`, use
    the function `edit_git_config`” (in general, `package::function`).

3.  In your **Console** pane (left-hand pane), type the following
    pressing Enter/Return after each line:

    ``` r
    library(usethis)
    edit_git_config()
    ```

    A file should open in the pane above your **Console** that is called
    `.gitconfig`. In this file, copy the information provided below,
    then update it with your preferred name (or pseudonym) and email
    (can be any email, but it would probably be helpful to use the same
    one you signed up for GitHub to avoid confusion). This information
    will be publicly available.

        [user]
          name = "name"
          email = "user@subdomain.domain"
        [credential]
          helper = cache --timeout=10000000

    Note that the lines begining with a left square bracket (`[`) start
    at the left most entry position and the lines that do not begin with
    a left square bracket have two spaces, then the information.

    Also note that we are instructing RStudio to remember your GitHub
    credentials for 10,000,000 seconds (or roughly 16 weeks) in the
    `[credential]` portion. RStudio is not remembering your credentials
    yet, but we will resolve this shortly.

4.  Click on the
    <img src="README-img/save-icon.png" alt="save" width = "20"/> icon
    and you can close this `.gitconfig` file.

<img src="README-img/noun_pause.png" alt="pause" width = "20"/>
<b>Planned Pause Point</b>: If you have any questions, contact Bradford
or another group.

### ☑️ Tasks 4: Connect RStudio and GitHub

Now that you have Git set up within RStudio, we can enable RStudio and
GitHub to communicate. To do this, we will need your GitHub username and
a Personal Access Token (PAT). PATs are designed to be more secure than
your password when communicating between your computer session and
GitHub. Conveniently, `{usethis}` has a function for this!

1.  To create a PAT, type the following in your **Console** and press
    Enter/Return:

    ``` r
    create_github_token()
    ```

    Note that you previously loaded `{usethis}` (using
    `library(usethis)`) so I did not ask you to do this again. **Once
    you load a package in your current RStudio session, you do not need
    to load it again.**

2.  You will be directed to a “New personal access token” page on GitHub
    in your browser. Since I work on multiple machines (i.e., my
    personal laptop, my work laptop, my personal desktop, and the
    RStudio Workspace), I like to provide a unique name for each PAT.
    For example, in the **Note** text field, I called this token “GVSU
    RStudio Workbench”.

    Most of the other options you will accept the default selections.
    However, you might want to change the **Expiration** date. A couple
    of suggestions: have this PAT expire at the end of this semester
    (e.g., August 10, 2022) or (**risky**) choose “No expiration”. After
    choosing a PAT expiration, scroll down and click on the green
    **Generate Token** button.

3.  After clicking on **Generate Token**, you will be taken to a
    “Personal access tokens” page that has a seemingly random string
    presented to you beginning with `ghp_`. Keep this page open for a
    little bit (I will tell you when it is safe to close it), as once
    you close this page, you will never be able to view this PAT again!
    I highly recommend that you store this code somewhere safe (e.g., a
    password manager tool). However, if you do lose it, you can go
    through this process again to create a new one.

4.  Now we need to associate this PAT in RStudio so that RStudio can
    connect to your GitHub account. Back in your RStudio **Console**,
    type the following and press Enter/Return after each line:

    ``` r
    library(gitcreds)
    gitcreds_set()
    ```

5.  In your **Console** you will be asked to
    `? Enter password or token:` Paste your PAT here (NOT your GitHub
    password) and press Enter/Return. You should see a message similar
    to:

        -> Adding new credentials...
        -> Removing credentials from cache...
        -> Done.

<img src="README-img/noun_pause.png" alt="pause" width = "20"/>
<b>Planned Pause Point</b>: If you have any questions, contact Bradford
or another group.

### ☑️ Tasks 5: Clone GitHub repo

Now that RStudio and GitHub are connected, we can clone this repo (i.e.,
copy the repo to our RStudio session)!

1.  In RStudio, click on the
    <img src="README-img/rproj-icon.png" alt="RStudio Project" width = "20"/>
    icon (the icon below the Edit drop-down menu);
2.  Click on **Version Control** on the *New Project Wizard* pop-up;
3.  Click on **Git** and you should be on a “Clone Git Repository” page;
4.  Back to your `activity01-rmarkdown` GitHub repo, click on the green
    **Code** button near the top of the page;
5.  Verify that **HTTPS** is underlined in red on the pop-down, then
    copy the URL provided;
6.  Back in RStudio, paste the URL in the “Repository URL” text field;
7.  The “Project directory name” text field should have automatically
    populated with `activity01-rmarkdown`. If yours did not, click into
    this box and press Ctrl/Cmd (usually this is a Mac issue);
8.  In the “Create project as subdirectory of” field, click on
    **Browse…**. Create a **New Folder** called “STA 418” of “STA 518”
    (depending on your course), then within this folder, create a **New
    Folder** called “Preparations”, think click **Choose**. Note that I
    am forcing you to use my file system management style.
9.  Click on **Create Project**.

Your screen should refresh and the **Files** pane should say that you
are currently in your `activity01-rmarkdown` folder that currently has
three files (`.gitignore`, `activity01-rmarkdown.Rproj`, and
`README.md`) and a folder (`README-img/`). If you are asked for your
GitHub credentials, provide your GitHub username and your PAT.

<img src="README-img/noun_pause.png" alt="pause" width = "20"/>
<b>Planned Pause Point</b>: If you have any questions, contact Bradford
or another group.

### ☑️ Tasks 6: Complete the `Rmd` file

For the rest of this class period, you will complete the RMarkdown
document (`activity01-bechdel-test.Rmd`) with your group members.
Bradford will continue circling through the groups and be available to
help when needed.

<!-- If you wish, this would be a good time to flip roles.-->

1.  Verify that you are in your forked version of this rep - your page
    title should be `username/activity01-rmarkdown`, where `username` is
    replaced with your GitHub username.
2.  In the main repo page on GitHub, click on the green **Code** button.
    Verify that **HTTPS** is underlined in red on the pop-down, then
    copy the URL provided.
3.  In RStudio, click on the
    <img src="README-img/rproj-icon.png" alt="RStudio Project" width = "20"/>
    icon (the icon below the Edit drop-down menu),
4.  Click on **Version Control** on the *New Project Wizard* pop-up,
5.  Click on **Git** and you should be on a “Clone Git Repository” page,
6.  Paste the URL in the “Repository URL” text field,
7.  The “Project directory name” text field should have automatically
    populated with `activity0101-rmarkdown`. If yours did not, click
    into this box and press Ctrl/Cmd (usually this is a Mac issue);
8.  In the “Create project as subdirectory of” field, click on
    **Browse…**. Navigate into your “STA 418” of “STA 518” (depending on
    what you created in Preparation 2), then within this folder, create
    a **New Folder** called “Activities”, think click **Choose**. Note
    that I am forcing you to use my file system management style.
9.  Click on **Create Project**.

You are probably currently in the `main` branch (the drop-down menu next
to the <img src="README-img/branch.png" alt="branch" width = "20"/> icon
in the **Git** pane). We will continue working within your main branch,
but I want you to notice that you can create new branches within
RStudio!

<!--
- In the RStudio **Git** pane, click on the <img src="README-img/branch.png" alt="branch" width = "20"/> icon,
- In the pop-up window, give your branch a name and click **Create**.
-->

In the **Files** pane, click on the `activity01-bechdel-test.Rmd`.
Update `author: "Name"` to your name.

Do not continue in this README document until after your group has
completed the `.Rmd` file, then stage, commit, and push to this to your
repo.

![Did you see… the memo… about
this?](https://media.giphy.com/media/lSVL6vdhdZVPW/giphy.gif)

<!--
## ☑️ Tasks 4: Combining your work

This works best if you and your Team Members can collaborate live with one another while you attempt to do it the first few times.
Have each member stage, commit, and push **only** the `activity0101-bechdel-test.Rmd` file to your individual GitHub branches.

With all of your individual branches pushed to GitHub, have each member create a **Pull Request**.
Make sure that you are pull requesting the the `main` branch (you want to send your individual branches to the combined `main` branch).

One member should serve as the "owner" (this is a role that this member is verbally agreeing to; there is nothing that needs to be done in RStudio or GitHub).
All other members will verbally assist the owner resolving the conflicts so that your final report on your `main` branch is complete and somehow a combination of each members work (you might need to do some additional editing).

The owner should now go back to their RStudio session.
Now, pull the changes that are on your Team's `main` branch by clicking on the <img src="README-img/pull-icon.png" alt="pull" width = "20"/> icon in the **Git** pane.

The owner should then switch to the `main` branch (this can be done by selecting `main` from the drop-down option next to the <img src="README-img/branch.png" alt="branch" width = "20"/>) icon.
Open the updated `activity0101-bechdel-test.Rmd` file.
Knit the updated RMarkdown document.
Finally, commit and push EVERYTHING to the `main` branch (select the check box next to all of the items).
Verify that your `main` branch on GitHub has everything.
-->

**YOU DID IT!**

**Next**: Activity 2 will cover creating visual representations of data.

## Attribution

This document is based on David Keyes’s tutorial at [R for the Rest of
Us](https://rfortherestofus.com/2021/02/how-to-use-git-github-with-r/),
[Happy Git with R](http://happygitwithr.com/) by Jenny Bryan et al.,
[The Coding
Train’s](https://www.youtube.com/channel/UCvjgXvBlbQiydffZU7m1_aw)
GitHub YouTube video series, and [The
Carpentries’](https://carpentries.org/) Git training.
