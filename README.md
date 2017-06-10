## Tutorial for learning how to use git/github. 
1. Download git onto your laptop. It can be found at https://git-scm.com/download/mac and follow the instructions to install  on your laptop 
2. Create an account on github.com and start your first project. Create an empty project with a Single Readme.md file
3. Understand the Markdown file format and start documeting your project with a well structured README.md file. 
4. On your laptop clone the new repository you created on github.com to create a local copy of the repo. <pre><code>git clone https://github.com/seshuad/github-101.git </code> </pre>
5. You can work on the local copy of the repo to add files and make revisions to those files. 
6. We will create a directory and add files to this local repo. 
<pre><code>
$ cd github-101
$ ls
README.md
$ mkdir src
$ cd src
$ cp /tmp/hello.scala .
$ git add hello.scala
$ git commit -m -m "Added the first source file to the new repos"
[master b9058bf] Added the first source file to the new repos
 1 file changed, 9 insertions(+)
 create mode 100644 src/hello.scala
$ git log
commit b9058bf686dbd2f80f34c648f5c768d6f2903e8d
Author: sadunuthula <sadunuthula@ebay.com>
Date:   Sat Jun 10 07:06:29 2017 -0700

    Added the first source file to the new repos

commit 44185e626de9af47bba2016bd25037d7a1121b5a
Author: seshuad <seshu.adunuthula@gmail.com>
Date:   Sat Jun 10 06:47:33 2017 -0700

    Create README.md

commit 9f4095efc6cdeee88d16d61ad18d2c5d81a38a17
Author: seshuad <seshu.adunuthula@gmail.com>
Date:   Sat Jun 10 06:46:02 2017 -0700

    Initial commit
$
</code>
</pre>
7. The repository with the code is now on your local laptop and needs to be pushed to the remote repository on github.com. 
<pre>
<code>
$ git push origin master
Counting objects: 6, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (5/5), done.
Writing objects: 100% (6/6), 736 bytes | 0 bytes/s, done.
Total 6 (delta 0), reused 0 (delta 0)
To https://github.com/seshuad/github-101.git
   108f1b8..44c8c9d  master -> master
$ 
</code>
</pre>
8. Now we will learn how to collaborate with others and allow multiple people to make changes to this repo. If your team member makes changes to the source and pushes these changes to github now you need to pull these changes onto your local repository. 
<pre>
<code>
$ git pull
remote: Counting objects: 3, done.
remote: Compressing objects: 100% (2/2), done.
Unpacking objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
From https://github.com/seshuad/github-101
   44185e6..108f1b8  master     -> origin/master
Merge made by the 'recursive' strategy.
 README.md | 42 +++++++++++++++++++++++++++++++++++++++++-
 1 file changed, 41 insertions(+), 1 deletion(-)
$ ls
</code>
</pre>
9. Your local repository is now syncrhronized with the remote copy on github.com. There can be conflicts during the pull if you happen to change a file on the local repo and the same file was modified on the remote as well. If there are conflicts that cannot be automerged git creates a version of the file that needs to be modified to resolve conflicts 


