# WEEK TWO

Remember last week, when I said that I have to finish the **maven** thing. Well, I
finished it in the first couple of minutes of monday, wasn't as much work left as I
expected. This task was quite interesting, since it probably will not be the last
time I will see **maven**.

I move on to coding a programm that loads a PNG file, translates it into a January
Dataset, is capable of doing changes to it, and then translates it pack to PNG. I
worked on this quite a bit. I managed to do a first version of it, and got started
on a second one which would use a more things from the january classes.

While I was working on that, we reviewed the **maven** thing I did. And what came out is
that the dependencies are missing in the pom files, wich makes the end-user duplicate
them. So adding them was my next goal.

Like last week working on maven was a lot of trial and error. And after some time I
finnaly managed to add the dependencies and clean up the pom files from week one,
because I added a lot of unnecessary stuff. Here it is on Maven central: [link](https://search.maven.org/#artifactdetails%7Ccom.github.yannick-mayeur%7Corg.eclipse.january%7C2.0.1%7Ceclipse-plugin).

I did a pull request to add my changes to the project (https://github.com/eclipse/january/pull/160). But there still some fixes needed before it is added to the master branch.

In parallel to that I also fixed another minor thing on maven (https://github.com/eclipse/january/pull/163).
You can now build January on Windows using maven without having to change things in maven,
because it is trying to execute an sh file.

Overall week two was in the continuity of week one, as I continued to work on maven.
Maven is now a tool I am getting more and more familliar with.
