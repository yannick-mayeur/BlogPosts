# WEEK THREE:

A new week, a new project. Indeed this week I am, along with the other interns introduced
to a new project: Eclipse CDT, an eclipse IDE for c and c++. To get us to know the project
a bit more, and to get used to gerrit which is going to replace the "pull request" in this
project we are asked to fix some minor bugs in the code.

After some struggle, the real job begins. I start to work with Pierre on [Bug 515296](TODO).
An editor telling the user a source file is not found is showing on eclipse when it is the
case. But in some cases the user doesn't want this information, so he should be able to
turn off.

We start by adding the option to either show or not this editor. The option is under the
form of a checkbox in the editor and in the main preference page of Eclipse CDT.

While this change was reviewed we started to work on another bug in parallel:
[Bug 515513](TODO). Some tests are failling on windows, see [lastest test results](https://hudson.eclipse.org/cdt/job/cdt-master-windows/lastCompletedBuild/testReport/).
So we started looking into them one by one, trying to figure out why they are failling,
and find a solution so they don't anymore.

After our change passed all the reviews we continued on the editor problem, we are now
trying more precise options so the user can decide to show it only in the usefull cases.
We probably will continue this task next Monday.
