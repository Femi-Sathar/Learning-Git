# Learning-Git
<br/>
<section>
<h1>Understanding Version Control,Why Git?</h1>
  <ul>
  <li> Let's say that you created a new code file and written a few lines in it - codefile1.</li>
  <li>Now you decide to put it under version control using Git</li>
  <li>let's say that you call this save point as number 1 - <strong>version1</strong></li>
  <li>later on as you progress you write maybe a few more lines of code</li>
  <li>And at this point you decide to make another save point and I call this <strong>second version.</strong></li>
  <li>So further down the line you accidentally screw up your entire code file and it's irreparable </li>
  <li>you simply just want to roll back to the last save point or need to find what changes you have made.</li>
  <li>you can do that using Git.</li>
  <li> So you can either compare your current code file so the current mess that you've made against a previous version so that any of the save points before.</li>
  <li>Alternatively you can simply just roll back to a previous version and it doesn't have to be the one that was immediately previous.</li>
  <li>You can go as far back or as far forwards as you like as long as you know which version you want.</li>
  </ul>
  </section>
  
  <section>
<h1>Version control using the git and the command Line </h1>
<ul>
<li>  Navigate to the working directory.So the working directory is the folder or the directory where you initialize your local Git repository.</li>                                                            
<li>  let's create a Git local repository and start tracking some of these file changes.</li>                             
<li>  So to initialize Git we simply write <strong>git init</strong>.</li>                            
<li>  And as you can see it's initialized and empty Git repository inside the story directory.</li>
<li>  if you use ls <strong>-a </strong>you can see .git file</li>
<li>  .git is going to be used to track all your changes, to commit your changes and to perform version control.</li>
<li>  And here in order to start tracking the changes of your files for example chapter1.txt, then you need to add this file to what's called a <strong>staging area.  </strong></li>
<li>  And that is basically a intermediate place where you can pick and choose which files inside your working directory that you want to commit.</li>
<li>  So to see what's currently inside your staging area, you can use the <strong>git status</strong> command. And it shows</li>
<li>  you that there are untracked files which will be shown in red and this is something that simply inside your working directory,</li>
<li>  but it's not yet in the staging area.So in order to add it to the staging area and to start tracking changes in it, then </li>
<li>  you have to use the command <strong>git add</strong>. So can type git add chapter1.txt or can add all files using <strong>git add .</strong></li>
<li>  So files is now in the staging area and it's ready to be committed. So the command is <strong>git commit -m "add a commit message"</strong>.</li>
<li>  So the commit message is really really important.commit message is something that helps you keep track of what changes you have made in each commit.</li>
<li>  So when you create a new save point, you want to be as explicit as possible about what changes were made between the last save point and this current save point.</li>
<li>  commit message is something that helps you keep track of what changes you have made in each commit.</li>
<li>  you can see what commits you have madeby using the <string>git log </strong>command.So you can see that this commit was made at this time by this person.</li>
<li>  And it also has a hash and this hash uniquely identifies this particular commit. And then right at the end you see this commit message of what this save point was all about.</li>
</ul>  
</section>
<section>
<h1>why there is a need for staging area</h1>
<ul>
<li>Now the reason why there is this intermediate staging area because you might wonder, why not just gofrom the working directory straight to the repository?</li>
<li>Why do we need this extra step?</li>
<li>Well sometimes you might not want to add all of your files to be tracked or all of your files to be committed.</li>
<li>So the staging area is a good place to try and figure out what are the things that you want Git to ignore nd what are the things that you want to be tracked.</li>
</ul>
</section>
<h1>To see the diff b/w wprking repo file and last save point use command <i>git diff</i>
<h1>Reverting changes made in working directory - <i>So git checkout name of file to revert</i></h1>
 
