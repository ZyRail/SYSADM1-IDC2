![Screenshot 2024-12-05 223958](https://github.com/user-attachments/assets/6cd5fc2d-26d4-4f37-9acf-6208c65040b8)

# SYSADM1 -- Git Basics

Answer the following research questions about Git, GitLab desktop and
GitHub.

1.  What is Git, and why is it important in software development?

-   Git is a repository that stores files and the changes made to each
    file over time. It is important in software development because it
    is mostly used for source code management. It has the ability to
    track changes in a stored file, giving the user the ability to
    manage and review their changes. Furthermore, git also allow its
    users to work collaboratively.

2.  How does Git track changes in a project?

-   Git thinks of its data as a stream of snapshots, every time a user
    commits or save the state of their project, git takes a picture of
    what your file looks like at that moment and stores a reference to
    that snachop.

3.  What is the difference between a local repository and a remote
    repository in Git?

-   A local repository in git allows its users to be more flexible in
    browsing accessing their projects/files because instead of accessing
    it on a remote server like in a remote repository, you can directly
    access it through your local database/ local disk.

4.  What are the basic Git commands?

-   Git add: move changes from the working directory to the tagging area

-   Git clean: removes untacked files from working directory

-   Git clone: creates copy of an existing git repository

-   Git commit: saves changes to a project/file

-   Git config: set configuration options

-   Got fetch: fetching downloads from another repository

-   Git init: initializes a new get repository

-   Git Log: explore previous revisions of a project/file

-   Git pull: automated version of git fetch

-   Git push: moving projects to another repository

5.  How do you check the status of a Git repository?

-   Use the command "git status" to check which files are in which
    state.

6.  What is the purpose of branches in Git, and how do you create and
    switch between them?

-   Branches in Git simply means a lightweight movable pointer to every
    commit made by a user. As a user starts making commits, a master
    branch is given to them that points to the last commit they made.
    Every time the user commit, the master branch pointer moves forward
    automatically. *A master branch is like any other branch, the only
    reason why nearly every repository has one is because using the "git
    init" command creates it by default and most user don't bother
    changing it.*

7.  What are GitLab Desktop and GitHub, and how are they different from
    Git?

-   GitLab and GitHub are both web-based Git repositories. Although both
    are developed by different companies, they still function the same.
    They share few functions such as, they offer clod-base storage, they
    contain issue trackers that allow users to resolve problems
    simultaneously, they run on linux servers, they have free and paid
    plans, they support open-source code and projects facilitating
    collaboration between users, they utilize mixed-programming models
    and many more. In comparison to both, Git is an open source version
    control system (VCS) used by DevOps teams to handle small to large
    software development projects. Unlike GitLab and GitHub, Git is a
    standalone tool that doesn't rely on central repositories. However,
    Git also has the ability to track changes and therefore supports
    non-linear development, allowing multiple members a team to modify,
    add, or delete files at any time.

8.  How do you connect a local Git repository to a GitLab or GitHub
    repository?

-   To be able to connect a local Git repository to a GitLab or GitHub
    repository use the following commands:

```{=html}
<!-- -->
```
-   Initialize the local repository

> : git init

-   Add remote repository

> : git remote add origin \<repository_url\>

-   Verify connection

> : git remote -v

-   Push local repository to the remote

> : git push -u origin main

9.  What are the steps to collaborate with others using GitLab or
    GitHub?

-   Steps:

```{=html}
<!-- -->
```
-   Clone repository

> : git clone \<repository_url\>

-   Create new branch

> : git checkout -b feature-branch-name

-   Make changes and commit

> : git add .
>
> : git commit -m \"Descriptive commit message\"

-   Push the branch to the remote repository

> : git push origin feature-branch-name

10. How do you resolve merge conflicts in Git?

-   Steps that could reduce the steps needed to resolve merge conflict
    in Git:

```{=html}
<!-- -->
```
-   Make any necessary changes to the conflicted file

-   Use "git add" command to stage the new merged content after making
    changes

-   Create new commit

```{=html}
<!-- -->
```
-   Git commands to resolve conflict:

```{=html}
<!-- -->
```
-   git log --merge

> : produce the list of commits causing the conflict

-   git diff

> : identify differences between the states of repositories or files

-   git checkout

> : undo changes to the working directory

-   git reset --mixed

> : undo changes to the working directory and the staging area

-   git merge --abort

> : exits the merge process and returns to the state before the merging
> began

-   git reset

> : use at the time of the merge conflict to rest the conflicted files
> to their original state.

11. What is a pull request, and why is it used in GitHub?

-   Git pull command fetches changes from a remote repository and
    integrates them into the current branch ensuring that your working
    directory is in sync with the changes made by other in your team.

12. What are some best practices for writing commit messages?

-   According to Sabotin (2023), a well-crafted commit messages not only
    document the history of the project but also facilitate
    collaboration and maintainability. Here are the 7 rules for
    effective commit messages he specified.

1.  Separate the subject from the body with a blank line

2.  Limit the subject line to a max of 20 characters

3.  Start the subject line with a lowercase letter and use present tense

4.  Avoid ending the subject line with period

5.  Use the imperative mood in the subject line

6.  Wrap the body at a max of 72 characters per line

7.  Utilize the body to explain the "what" and "why" of the changes
    rather than the "how"

References:

> Afreen, S. (2024, July 15). *How to resolve merge conflicts in Git?*
> Simplilearn.com.
> https://www.simplilearn.com/tutorials/git-tutorial/merge-conflicts-in-git#:\~:text=Step%201%3A%20The%20easiest%20way,of%20the%20git%20commit%20command.
>
> Atlassian. (n.d.). *Basic Git Commands \| Atlassian Git Tutorial*.
> https://www.atlassian.com/git/glossary#commands
>
> Computing, R. (2024, October 24). The differences between Git, GitHub,
> and GitLab. *Rheinwerk Computing*.
> https://blog.rheinwerk-computing.com/the-differences-between-git-github-and-gitlab
>
> *Git - What is Git?* (n.d.).
> https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F
>
> *Git, GitHub, and GitLab: What's the difference? \| BairesDev*. (2022,
> October 26). BairesDev.
> https://www.bairesdev.com/blog/git-github-and-gitlab-whats-the-difference/
>
> Subotin, O. (2023, September). *7 Best practices of Git Commit
> Messages*. Codefinity.
> https://codefinity.com/blog/7-Best-Practices-of-Git-Commit-Messages
