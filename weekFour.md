# WEEK FOUR: Get started with gerrit on CDT

You are maybe familiar with the pull request system of **GitHub** programmers
(you) use to contribute to an open-source project. **Gerrit** basically is an
improved version of this system. It allows the committer to give more precise
feedback on each line of code you changed, and is more complete overall.
**Eclipse CDT** uses **gerrit** for the community to contribute. In this blog
post I will try to show you how to efficiently get started with it.

## The required tools & knowledge

Having git is basically all you need to get the sources, and push them. If you
want to edit them in a good environment use the [Eclipse JAVA
IDE](https://eclipse.org/downloads/packages/release/Neon/3). Knowing the basics
of git is also required even thought I think you could learn git and this at
the same time, it will just take a little more practice and tries.


## The required tools & knowledge

Having git is basically all you need to get the sources, and push them. If you
want to edit them in a good environment use the [Eclipse JAVA
IDE](https://eclipse.org/downloads/packages/release/Neon/3). Knowing the basics
of git is also required even thought I think you could learn git and this at
the same time, it will just take a little more practice and tries.

## How to get the sources of CDT

Cloning the sources to your computer is an easy but essential task. Getting
them is fairly easy.

The link of the repository is:
git://git.eclipse.org/gitroot/cdt/org.eclipse.cdt

To clone use the following command: `git clone
git://git.eclipse.org/gitroot/cdt/org.eclipse.cdt`

Once you have the files, get to [bugizlla](TODO) and find a bug you want to
fix.

## Pushing the changes to Gerrit

Now comes the hard part. In order for you to be able to push your change a
couple things have to be respected.
* Only one commit per change
* You have to sign of you commit using: `git commit -s`
* You must have signed the [ECA](https://www.eclipse.org/legal/ECA.php) with
  the same email adress you use for git
* Your commit must have a changeId. In order for you commits to automatically
  add a changeID you can install a hook. To install a hook, go into root
directory of the project and execute following command: <br> `curl
-Lo.git/hooks/commit-msg http://review.example.com/tools/hooks/commit-msg`
* Add the gerrit remote, by using one of the following links:
  http://git.eclipse.org:29418/cdt/org.eclipse.cdt.git or
ssh://commiterId@git.eclipse.org:29418/cdt/org.eclipse.cdt.git if you are using
ssh. Add the remote with the following command: `git remote add linkOfRepo`

When all this is done you can push with: `git push gerrit
HEAD:refs/for/master`.

An Eclipse commiter will go thourgh you changes and review them. You will be
notified per email once this review is done. If the change is accepted well
done, if not you will have to do all request changes before pushing again but
by keeping the exact same changeID.

## Collaborative work

Working in collaboration with someone on git ain't the easiest thing, so let me
give some tips and tricks I would have liked to know beforehand.

* If you are working with someone on the same gitter change, you can add this
  to your commit message:<br> `also-by name <email>`.

* To get what you collaborator has pushed to gerrit but keeping your changes
  you can use cherry-pick.

  ![cherry-pick](ressource/w4-1.png)

  It may happen that you get some conflicts, manually merge the confilicted
files and continue the cherry-pick with:<br> `git cherry-pick --continue`. <br>
Merge your and his commit by squashing the commits with: `git rebase -i HEAD~2`
and changing `pick` to `squash` on the second commit.

* When you are working on an open-source project with like Eclipse CDT with an
  active community, commits happen quite frequently. If you want your change to
be on the lastest version of the project you may have to rebase it. Here is how
to do it:
  * checkout master
  * pull the changes
  * get back to your branch and do: `git rebase master`

## Conclusion

I worked on [Bug 515296](https://bugs.eclipse.org/bugs/show_bug.cgi?id=515296)
with Pierre Sachot. So we both had to learn how to use git at our advantage. By
the end of the week, and a couple reviews later we were very near to having
achieved the fix and it being pushed to the main repository of **Eclipse CDT**.


better conclusion
