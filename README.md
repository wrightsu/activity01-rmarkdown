Activity 1 - Resolving Merge Conflicts
================

We will begin this activity as a whole class, then breakout into Teams.
It is assumed that you have watched the videos contained within
Preparation 1.

In this activity, you will:

-   Connect GitHub and RStudio and share files between these two tools.
-   Edit and view changes in narrative text and R code chunks in an
    RMarkdown document.
-   Create a branch within a GitHub repository.
-   Fork a repository and make a pull request.
-   Resolve merge conflicts caused when multiple users edit a file at
    the same time.

## ☑️ Task 1: Forking A Collaborative Poem

In this activity, we begin collaborating on coding projects.
Collaborating on projects might be with you and colleagues **or**,
simply, you and future you. Version control is one way to keep track of
what a person did and when, which is much better than this system:

![“Piled Higher and Deeper” by Jorge
Cham](http://phdcomics.com/comics/archive/phd101212s.gif)

The Google Workspace (Drive, Docs, etc.) is a spectacular tool to use to
collaborate on many different types of projects. Google even has a
collaborating on coding notebooks (i.e., [Google
Colab](https://youtu.be/inN8seMm7UI)); however, but is lacking in
programming language options. We can think of GitHub as a Google Drive
for collaborating on coding/software projects. Git would then be like
[Version History](https://support.google.com/docs/answer/190843?hl=en)
for a Google Doc.

Version control systems record the changes that are made each step of a
project. This allows you to rewind to start at a previous version and
play back through changes you made to eventually arrive at the most
recent version. This is similar to what you did in your Learning Journal
entry for Preparation 1.

![Changes are saved sequentially](README-img/recording-changes.svg)

Each time you make changes, you can (and should), provide a brief, yet
informative commit message. This commit message is additional
information that can be used to help keep track of what changes were
made. There are many opinions on what needs to be included in commit
messages. My recommendation is to use active terms and be brief, but say
enough as to *why* this change was needed. Note that I do not always
follow this recommendation (I get lazy too), but future me really
appreciates it when current me is thoughtful.

### A brief demonstration

Recall Daniel from The Coding Train’s video - he was working on a
collaborative poem with different versions of hisself. I am going give a
brief demonstration that *quickly* goes through:

1.  Connecting RStudio and GitHub,
2.  Creating a branch in GitHub and making and committing changes on
    this branch,
3.  Creating a branch in RStudio and making and committing changes on
    this branch,
4.  Merging these branches to the `main` bran in GitHub.

To see Daniel from The Coding Train work through a similar process on
his collaborative poemk, checkout:

[![Resolving Merge
Conflicts](http://img.youtube.com/vi/JtIX3HJKwfo/0.jpg)](http://www.youtube.com/watch?v=JtIX3HJKwfo "1.9: Resolving Merge Conflicts - Git and GitHub for Poets")

<img src="README-img/noun_pause.png" alt="pause" width = "20"/>
<b>Planned Pause Point</b>: If you have any questions, contact your
instructor or another group.

## ☑️ Task 2: Talking with your Team

From your Preparation 1, you saw that if you (individually) made changes
to a branched version of your document, then merged those back into your
`main` branch, there were no issues with the merge. In fact, two people
could be editing the same file (on the same branch) and commit changes
with no issues as long as the edits do not occur on the same line.

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
neighbor(s).

If you do not know your neighbor, introduce yourself!

Before we get into “doing” stuff, in addition to this `README.md` file,
there are a four versions of the same document within the `docs/`
directory/folder of this activity repo:

1.  `day1.md`,
2.  `day1.html`
3.  `day1.pdf`, and
4.  `day1.Rmd`.

With your neighbor, explore how each file looks within your repository
(click on them to view them within GitHub). Discuss with your Team
members what is easily viewable and what is not. Keep this in mind as we
progress through this semester.

Jenny Bryan provides some great information on [repo
browsability](https://happygitwithr.com/workflows-browsability.html).
Throughout this course, we will use my opinionated method of repo
organization.

Now onto some doing. **Important**; take these next steps slowly and
communicate with your Team members. When you run into an issue, get a
hold of me or another group.

When people are collaborating, they will likely step on one another.
This can even happen if an individual person is working on files from
their laptop and a school computer. We will now force a conflict, then
work to resolve overlapping changes.

When changes are made to the same line, we must decide which change we
want to keep (or further edit them to implement both).

![Conflicting changes](README-img/collaborating-conflict.svg)

Have one group member serve as the repo “owner” and the other(s) will be
a “collaborator”. The owner should grant the collaborator(s) access to
their `<username>/activity0101-merge-conflicts` repo:

1.  Click on ![settings icon](README-img/settings.png) **Settings** tab
    on the top menu,
2.  On the settings page, click on **Manage access** on the left-hand
    toolbar,
3.  Click on the green **Invite teams or people** button, search by your
    group members username, and select them.

The collaborator can accept this invitation by either click on the link
that was emailed to the account attached to GitHub or type the following
in their browser, where `<owner>` is the owners GitHub username:

`https://github.com/<owner>/activity0101-merge-conflicts`

Now, each group member should create their own branch within the owner’s
repo (name this your name or GitHub username).

In your personal branch, open the `day1.md` file and edit this document.
Each person will make a similar change to force the need for a merge
conflict:

1.  Create a new line 4 (press Enter/Return at the end of line 3 so that
    line 4 is now blank),
2.  Type `author: "First Last"` on this new line 4, where each member
    provides their first and last name (or pseudonym for those wanting
    to maintain some level of anonymity),
3.  Provide a meaningful commit message (and more descriptive message if
    so desired) and commit your changes.

Now, each member will create a **Pull Request** to add these changes
back to the `main` branch.

1.  Click on ![merge icon](README-img/merge.png) **Pull requests** tab
    on the top menu,
2.  On the pull requests page, click on the green **New pull request**
    button,
3.  On the “Comparing changes” page in the gray area with the ![compare
    icon](README-img/compare.png) icon, you want the left-hand selection
    to be `base: main` and the right-hand selection to be the member’s
    branch (to request that the `main` branch pulls in the member’s
    branch),
4.  The screen will refresh with a snapshot of the changes at the
    bottom. For the time being, simply click on the green **Create pull
    request** button,
5.  Provide a meaningful commit message (and more descriptive message if
    so desired) and create your pull request.

You will be taken to another page, but for now go back to the repo’s
main page. The owner will now make decisions with respect to how these
changes should be pulled in. The collaborators should help the owner
through this process.

1.  The owner should go back to the to the ![merge
    icon](README-img/merge.png) **Pull requests** tab on the top menu.
    All current pull requests will be listed near the bottom of the
    page. The owner should click on their pull request and accept the
    changes. There should be no issues.
2.  The owner will do this for each of the remaining pull requests
    except there will be issues. As a team, decide what information to
    keep (remember that you can keep both like we did in our example),
    then complete the pull request.
3.  You can choose to completely close the pull request or keep them
    viewable here. You can always view closed pull requests by toggling
    that filter.

Congratulations, you collaborated on a GitHub project! As we progress
through this semester, remember to take things slow and reach out when
you run into problems. Together, all things are possible. If there is
time at the end of class, we will do this with the other members being
the repo “owner”. However, there will be a lot of opportunities to
continue practicing this throughout the semester. Note that to be able
to collaborate (submit pull requests) to a GitHub project, users do not
need to be contributors. They can fork the repo, make edits, and submit
a pull request.

Look through your `<owner>/activity0101-merge-conflicts` repo’s commit
history. Remember from The Coding Train’s videos that you can view the
commit history via the ![Clock
history](README-img/noun_clock_history.png) icon or **Network** graph in
the ![line graph](README-img/noun_line_graph.png) **Insights** tab.

<img src="README-img/noun_pause.png" alt="pause" width = "20"/>
<b>Planned Pause Point</b>: If you have any questions, contact your
instructor or another group.

## ☑️ Tasks 3: Complete the RMarkdown Document

For the rest of this class period, you will complete the RMarkdown
document (`activity0101-bechdel-test.Rmd`) with your group members. Your
instructor will continue circling through the Teams and be available to
help when needed.

If you wish, this would be a good time to flip roles.

1.  In the main repo page on GitHub, click on the green **Code** button.
    Verify that **HTTPS** is underlined in red on the pop-down, then
    copy the URL provided.
2.  In RStudio, click on the
    <img src="README-img/rproj-icon.png" alt="RStudio Project" width = "20"/>
    icon (the icon below the Edit drop-down menu),
3.  Click on **Version Control** on the *New Project Wizard* pop-up,
4.  Click on **Git** and you should be on a “Clone Git Repository” page,
5.  Paste the URL in the “Repository URL” text field,
6.  The “Project directory name” text field should have automatically
    populated with `activity0101-merge-conflicts`. If yours did not,
    click into this box and press Ctrl/Cmd (usually this is a Mac
    issue);
7.  In the “Create project as subdirectory of” field, click on
    **Browse…**. Navigate into your “STA 418” of “STA 518” (depending on
    what you created in Preparation 2), then within this folder, create
    a **New Folder** called “Activities”, think click **Choose**. Note
    that I am forcing you to use my file system management style.
8.  Click on **Create Project**.

You are probably currently in the `main` branch (the drop-down menu next
to the <img src="README-img/branch.png" alt="branch" width = "20"/> icon
in the **Git** pane).

If you closed the branches in the previous task, create a new one.

-   In the RStudio **Git** pane, click on the
    <img src="README-img/branch.png" alt="branch" width = "20"/> icon,
-   In the pop-up window, give your branch a name and click **Create**.

If you did not close the branches, select your personal branch from the
drop-down options.

In the **Files** pane, click on the `activity0101-bechdel-test.Rmd`.
Update `author: "Name"` to your name (we will combine these at the end
with a pull request).

Do not continue in this README document until after your group has
completed the `.Rmd` files and pushed to their `<username>` branches.

![Later… from Spongebob
Squarepants](https://i.ytimg.com/vi/tS9DkqgS488/maxresdefault.jpg)

## ☑️ Tasks 4: Combining your work

This works best if you and your Team Members can collaborate live with
one another while you attempt to do it the first few times. Have each
member stage, commit, and push **only** the
`activity0101-bechdel-test.Rmd` file to your individual GitHub branches.

With all of your individual branches pushed to GitHub, have each member
create a **Pull Request**. Make sure that you are pull requesting the
the `main` branch (you want to send your individual branches to the
combined `main` branch).

One member should serve as the “owner” (this is a role that this member
is verbally agreeing to; there is nothing that needs to be done in
RStudio or GitHub). All other members will verbally assist the owner
resolving the conflicts so that your final report on your `main` branch
is complete and somehow a combination of each members work (you might
need to do some additional editing).

The owner should now go back to their RStudio session. Now, pull the
changes that are on your Team’s `main` branch by clicking on the
<img src="README-img/pull-icon.png" alt="pull" width = "20"/> icon in
the **Git** pane.

The owner should then switch to the `main` branch (this can be done by
selecting `main` from the drop-down option next to the
<img src="README-img/branch.png" alt="branch" width = "20"/>) icon. Open
the updated `activity0101-bechdel-test.Rmd` file. Knit the updated
RMarkdown document. Finally, commit and push EVERYTHING to the `main`
branch (select the check box next to all of the items). Verify that your
`main` branch on GitHub has everything.

**YOU DID IT!**

![denzel
washington](https://media.giphy.com/media/l0Iy69RBwtdmvwkIo/giphy.gif?cid=ecf05e4726kfujh6vzssnilsm6n6gqt6rteytspbtbcaj4e9&rid=giphy.gif&ct=g)

**Next**: Activity 2 will cover creating visual representations of data.

### Acknowledgement

Parts of this README are based on [The Coding
Train’s](https://www.youtube.com/channel/UCvjgXvBlbQiydffZU7m1_aw)
GitHub YouTube video series and [The
Carpentries’](https://carpentries.org/) Git training.
