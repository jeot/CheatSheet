# reseting one file
To reset a specific file to the last-committed state (to discard uncommitted changes in a specific file):
    git checkout thefiletoreset.txt
This is mentioned in the git status output:
(use "git checkout -- <file>..." to discard changes in working directory)

# reset everything to last commit
To reset the entire repository to the last committed state:
    git reset --hard
To remove untracked files, I usually just delete all files in the working copy (but not the .git/ folder!), then do git reset --hard which leaves it with only committed files.

# clean working directory
A better way is to use git clean: (Warning: using the -x flag as below will cause git to delete ignored files.)
    git clean -d -x -f
will remove untracked files, including directories (-d) and files ignored by git (-x). Replace the -f argument with -n to perform a dry-run or -i for interactive mode and it will tell you what will be removed.
