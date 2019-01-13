git
^^^^

Repositories
--------------

We use Gitlab to host our all project code.

There are two repositories exist:

    * Backend: repository containing all server-side code
    * Frontend: repository containing the front-end code (future)


Git Rules
----------

Always pull the latest code from master code at the start of each day.
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
    Why? Sometimes, our awesome developers make changes to the data models on the
    server-side. This can affect how models are used when called. So, at the start of
    your day, always pull in the latest code from the staging branch for each
    repository.

Perform work in your own feature branch and never the staging.
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
    Why? This way, all work done in the feature branch is isolated from the staging
    branch. In addition, you can iterate your code changes without polluting the
    staging branch with potentially unstable code.

Always name your branches appropriately.
+++++++++++++++++++++++++++++++++++++++++
    Why? To make life easy for our beloved product manager, append the ticket number
    and a short description to your branch name in this format:

        * PE-{XXXX}/{Short Issue Description}
        (PE - because project name is Project Example)

    Keep the short description to 5 words or less. If you require more than 5 words,
    drop the short description altogether.

    Examples:

        * PE-17/Profile-Modal-Fix (default)
        * PE-18(if short description exceeds 5 words)

    As a general note: avoid taking the easy way out of dropping the short description.
    If the description requires more than 5 words, think of a more succinct way to
    describe it. We limit the characters, just like Twitter, to force you to be more
    succinct in describing an issue.

Make committing and pushing code changes to your branch as a habit
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
    Why? To avoid any data loss as a result of your laptop facing a misfortune, we encourage
    that you keep pushing your code to your local feature branch even if is still a work in
    progress.

Remove unnecessary code before pushing to your feature branch.
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
    Why? To make code reviews easier, remove any unnecessary lines of code. This could include
    code snippets that have been commented out and even debug functions (e.g. Javascript.console.log, pdb).

Whenever possible, add a comment describing your code functionality.
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
    Why? While not required, writing a short paragraph describing the functionality of your code
    will be certainly helpful for the understanding of everyone involved.

Don't be afraid to ask for help from other developers.
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++
    Why? The problems we try to solve can be difficult at times. Don't be afraid to ask for help.
    But remember: before you do,  be clear in the problem you face and the solutions you have explored
    but failed. It's also important that you push your code to your feature branch so that other
    developers can provide help.

Delete local and remote branches after your code has been merged into the staging branch.
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
    Why? Simple: we want to keep our repositories clean and organized.

Write good commit messages when pushing your code to any branch.
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
    Why? The success of the project rests (among other things) on maintaining a well-documented
    project log. When pushing code to your branch, it's worth taking the time to write clear,
    useful and helpful commit messages. What may be a hassle at first will ensure productivity
    for everyone involved. Keep your commit messages to 50 characters or less.

Send a merge request after you have finished your task.
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++
    Why? This is critical so that your code can go live on the server. Go to Gitlab. Request merge
    of your branch to indonesia/staging. Put short description of changes on that branch. The merge
    request should be Assigned to your project leader. He/She will provide comments (if necessary).
    Finally, when you are done with all code corrections, and your code has been accepted and merged
    into staging branch, the ticket can be Resolved.


Git WorkFlow
---------------

Cloning the repository
++++++++++++++++++++++++
You can choose to clone either via SSH or HTTPS. For instructions on how to set-up SSH, please refer to this
`Tutorial <https://docs.gitlab.com/ee/ssh/>`_.
::

    # SSH
    git clone git@gitlab.com...

    # HTTPS
    git clone https://gitlab.com...

Check out a feature branch
++++++++++++++++++++++++++++
If a remote branch already exists for the feature you've been assigned to work on, check out the branch.
::

    # Check remote branches
    git branch -r

    # Checkout the remote branch
    git checkout -b <branch name>

    # Pull the remote branch to your local branch
    git pull
If the branch is not yet exist on the remote repository, create a new local branch.
::

    git branch <new branch name>

Push your code to the repository.
+++++++++++++++++++++++++++++++++++
At the end of each day or upon completion of your task (whichever is earlier), push your code to your feature branch.
::

    # Add all current changes to the next commit. See: https://git-scm.com/docs/git-add
    git add .

    # Add a commit message. See: https://git-scm.com/docs/git-commit
    git commit -m <commit message>

    # Push your commit to the remote repository. See: https://git-scm.com/docs/git-push
    git push


Remove your local branch after the code has been merged into staging.
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Upon successful merging into staging, remove your local branch.
::

    git branch -d <branch name>
