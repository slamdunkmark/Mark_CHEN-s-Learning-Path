# Git命令学习 
## Basic workflow
### Diff 中表达的东西
    git diff report.txt
    
    diff --git a/report.txt b/report.txt
    index e713b17..4c0742a 100644
    --- a/report.txt
    +++ b/report.txt
    @@ -1,4 +1,5 @@
    -# Seasonal Dental Surgeries 2017-18
    +# Seasonal Dental Surgeries (2017) 2017-18
    +# TODO: write new summary

>* The command used to produce the output (in this case, diff --git). In it, a and b are placeholders meaning "the first version" and "the second version".
>* An index line showing keys into Git's internal database of changes. We will explore these in the next chapter.
--- a/report.txt and +++ b/report.txt, wherein lines being removed are prefixed with - and lines being added are prefixed with +.
>* A line starting with @@ that tells where the changes are being made. The pairs of numbers are start line and number of lines (in that section of the file where changes occurred). This diff output indicates changes starting at line 1, with 5 lines where there were once 4.
>* 所以我们应该是看第二个的数字，因为第一个一般就是个地址，感觉没有很大的参考价值。
>* A line-by-line listing of the changes with - showing deletions and + showing additions (we have also configured Git to show deletions in red and additions in green). Lines that haven't changed are sometimes shown before and after the ones that have in order to give context; when they appear, they don't have either + or - in front of them.


| 命令        | 解释   |
| :-------   | :-----  |
|git status|show which file is changed|
|git diff x|show the difference|
|git add x|add file x to the staging area|
|git diff -r HEAD|compare the all committed|
|git diff -r HEAD filepath|compare the committed in a file|
|git commit|save things in staging area|
|git commit -m "x"|commit change with a x message|
|git commit --amend -m "x"|change the commit message|
|git log|see the history of commit|
|git log path|see the history of commit of a file|



## Repositories

| 命令        | 解释   | 
| : --------   | -----  |
|git show xxx|find commit with commit hash(first few chars)|
|git show HEAD~1|refer to most recent commit|
|git annotate x|see who made the change of a file|
|git diff hash1(HEAD~1) HEAD~2|difference between 2|
|git add xx|status first, then add and commit|
|.gitignore file|ignore things in it, x for directory, x.jpg for files |
|git clean x|clean a file from stage|
|git clean -f x|clean a file and delete it|
|git config --list --local|settings for one specific project|
|git config --list --global| settings for every one of your projects|
|git config --list --system|settings for every user on this computer|
|git config --global setting value|change the git configuration|

## Undo

| 命令 | 解释 |
| ---- | ---- |
|      |      |
| : -------- | ----- |
| ---------- | ----- |
|            |       |




## Working with Branches
| 命令        | 解释   | 
| : --------   | ----- |
|git branch|See what branches in your repository|
|git diff branch1 branch2|check the difference between branches|
|git checkout x|switch to another branch|
|git rm x|remove the file in stage|
|git checkout -b x|create a branch x and switch to it|


## Collaborating

| 命令        | 解释   | 
| : --------   | ----- |
|git init xxxx|create a repository|
|git init xx(path)|change current project into git repository|
|git init|let the current directory to be git repo|
|git clone URL_or_path x|clone a repo as x|
|git remote|get the name of the remote repo originated|
|git remote -v|get the name and URL of remote|
|git remote add name URL|add the remote with URL|
|git remote rm name|remove the remote|
|git pull (remote) (branch)|pull the branch in remote and merge to your current branch|
|checkout+pull|you cannot pull the files once you have changes on that file|
|git push (remote) (branch)|push to the remote|
|add+commit+push|连接github的方法|

>* When conflict with others
    first: git pull remote branch -- to update and merge
    second: push again
