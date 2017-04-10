# WEEK ONE

It's sunday. This week I worked on a real IT project for the first time in
my life. First but not last that is for sure !

During the week I got introduced to a concept called the pull request and 
that is one of the things I am going to talk about in this post. But 
first let me properly introduce the project I am working on.

I am working on a project called **January** which stands for JAva NUmerical
ARrays, basicly it's numPy for Java. There are two companys
supporting the project: Diamond Light Source, and Kichwa Coders. I am 
working with Kichwa Coders.

So what is a **pull request**? To answer this question we have to
look at how an open source project works on **GitHub**. On GitHub when
you create a public project people like you and me can fork it, meaning
they are creating there own version of this very project. On this new
version of the project they can change things, and if they want to have
these changes implemented in the main project they have to do a **pull
request**. The owner can then either implement the feature or the fix, or
reject the request.

This concept is **very** important and will probably folow me during my
whole internship.

After doing some minor fixes (https://github.com/eclipse/january/pull/136
and https://github.com/eclipse/january/pull/141)to the project my real job 
began. I had to to rewrite the POM files of the **January** project in a way
so someone who wants to use **January** in his own project only has to import
it through maven's POM files. This was harder than I expected and I will have
to finish this next week.
