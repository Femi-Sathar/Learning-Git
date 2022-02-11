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
 <l1>To remove everything from staging area use <i>"git rm --cached -r ."</i></li>
</ul>
</section>

<h3>To see the diff b/w wprking repo file and last save point use command <i>git diff</i></h3>
<h3>Reverting changes made in working directory - <i>git checkout name of file to revert</i></h3>

<section>
  <h1>Github - Remote Repository</h1>
 <li>Create account ,login,create a new repo,mark public ,dont initialize a read me .go ahead and click the big green button and create repository.</li>
<li>So now you can see that there are two ways that they tell you you can set up your repository.</li>
<li>You can either set it up in GitHub for Mac on desktop their desktop client </li>
<li>But instead we can use command line instructions to set up our repository.</li>
<li>follow below steps before using command line instruction to add files to github</li>
<pre>
Step 1) You will need to config your git username and email with the following commands. This is assuming you setup your github account already:
             git config --global user.name 'Your Name'
             git config --global user.email 'your_email@example.com'
Step 2) You need to create an SSH folder for your SSH keys. From my understanding, its like a key that will link your computer to your github account. First you need to create a ".ssh" folder in the root directory
             cd ~/.ssh
Step 3)This is just following a lot procedures to follow to create your SSH key:
             eval `ssh-agent -s`
             ssh-keygen -t rsa -C "your_email@example.com"
You should see something like "Generating public/private rsa key pair". It will ask you file to save key, passphrase, passphrase again. I left all three blank and pressed Enter each time.
Once all this is done, you'll get a message along the lines of that your public key has been created at the SSH directory along with a unique key fingerprint ID. The last step is to add your new key to the SSH agent with the following:
    ssh-add ~/.ssh/id_rsa
<Step 4) Go to Account Settings on your GitHub account on your browser and click "SSH and GPC keys" tab and click "New SSH Key" button on top right of page.
<li>Set a title that makes sense for you. Something like "MyPC SSHkey".</li>
<li>For the "Key" textbox, you need to copy the key you generated in the previous step in the ".ssh" folder. Navigate to that folder and open the "id_rsa.pub" file with any text editor.</li> 
<li>Copy the key exactly as you see it. It should begin with "ssh-rsa".</li>
<li>Just click "Add SSH key" after that and you should be good.</li>
</pre>
<li>So we are going to push an existing repository that we've got locally onto this remote repository and to do that we need to copy the address of our GitHub  repository</li>
<li>and we're going to use two lines of code in order to transfer or push our existing local repository</li>
<li>from the command line. </li>
<li> - git remote add origin ur ssh path </li>
<li> - gitu push - u origin main</li>
<li>Now origin is simply the name of your remote, main is the master branch</li>
<li>And what this line of code does is that it pushes your local repository to the remote repository using the u flag or the u option which basically links up your remote and your local repositories.</li>
<li>we're going to push it towards the remote that's called origin and we're going to push it to the branch that's called master.So the master branch is simply the default branch or the main branch of all of your commits.</li>
<li>if everything is fine you can see message - branch 'main' set up to track 'origin/main'. in command line</li>
<li>our files are now hosted on GitHub and it's complete with all of our commit messages.</li>
<li>So if you go to insights, graphs and go into network, you can actually see our mass the branch which shows the save points .If you hover over them you can actually see the commit messages of each of these.</li>

<h3> Working file - > Staging Area - > Local Repository - > Remote Repository </h3>

</section>
<section>
<h1>gitignore</h1>
  <li>you might want to not upload certain things to GitHub, </li>
 <li>for eg files that are to do with your local settings or your user preferences.</li>
 <li>There's a whole bunch of these types of utility files that you don't really want another person to have</li>
 <li>to download and copy into their project folder if they're cloning or if they're forking your projects.</li>
 <li>eg- ur API keys or any secret information</li>
 <li>So a really common example that people tend to add to their gitignore files are what are called DS_</li>
 <li>Store files. S DS_Store files are basically a settings file that saves certain things like you know how</li>
 <li>you like your icons to be arranged in a particular project folder.</li>
 <li>so you can create a <i>.gitignore </i>file - touch .gitignore. to see file in folder user "ls -a", bcoz its hidden</li>
 <li>"open .gitignore" and add every files you dont want to commit for eg u can add secret.txt.</li>
 <li>you can use # sign to comment in .gitignore file</li>
 <li>you can use wildcard *.txt - > everything can be commited except all txt files</li>
 <li>Now if you do git add . and check git status you can see that secret.txt is ignored</li>
</section>

<section>
<h1>gitclone</h1>
<h3> Remote Repo -> Working Directory</h3>
<li>cloning a remote repository pull it into your local machine.</li>
<li>So this is called cloning or the command would be git clone and that is a way for you to pull down all</li>
<li>of the commits and all of the versions of a particular remote repository and to store the files inside</li>
<li>your working directory.</li>
<li>command - git clone URL of a particular remote repository </li>
<li>You can also use 'git log' to check out some of their previous commits and you can see they've got all</li>
<li>these commit messages that tell you what each commit was all about.</li>
</section>

<section>
<h1>Branching and Merging</h1>
<h3>Why we need to create branches?</h3>
<li>Now let's start off with a simple example say if we had version 1 and 2,</li>
<li>so two commits that were made to our local repository.</li>
<li>Now at this point we realize that we want to maybe try out something different, maybe build a new feature</li>
<li>or just to mess around with a new idea or concept.</li>
<li>So what we can do is instead of continuing to commit to the master branch which is the main branch ,</li>
<li>we can also create a side branch. So we can create as many branches as we like.</li>
<li>We can add some features and some code.</li>
<li>Now simultaneously we can continue working on the main branch putting out all those essential updates</li>
<li>or bits of code that are maintaining our main project but at the same time we can continue to update</li>
<li>and work on side branch</li>
<li>So now we have two branches that are parallel to each other and they can be developed simultaneously.</li>
<li>Now if at some point in the future that we decide that that side branch was really fruitful and the feature</li>
<li>that we built in it was really really great and we'd like to merge it back to the main branch or to</li>
<li>the main project, then that can be done really easily as well by simply placing a merge request in.</li>
<li>And we can bring all of those changes that we experimented with, that we messed around with back to the</li>
<li>main project and check to see if there's any conflicts with the main branch code.</li>
<br/>
<br/>
<li>very often what you see in practice is that there'll be multiple branches being worked</li>
<li>on at the same time for any given large project.</li>
<li>And the reason is because sometimes you are developing new features, </li>
<li>sometimes you are fixing bugs and all of these things may break your main project </li>
<li>so you don't want to do it on the master branch.</li>
<li>You only want to put it onto the master branch once you've tested, </li>
<li>once you know that everything is working fine and </li>
<li>then you can bring your code back to the working copy ready for shipment and deployment.</li>
<li><h3>How to create a branch<h3>
<li>To create a new branch you can simply just git branch specify the name of your</li>
<li>new branch. eg <i> git branch mysidebranch </i></li>
<li>To see all the branches you created use - <i> git branch </i> u can see main and mysidebranch</li>
<li>To switch to side branch - <i>git checkout sidebranch name</i>, you will get a message switched to side branch</li>
<li>Now you can modify files or create files and do git add . ,git commit ,to save to side branch. you can see modified files</li>
<li>To switch to main - git checkout main , you can open and see the files in main branch, its unchanged</li>
<li>you can see the local files changes when you switch branches </li>
<li>Now switch to main and do git log - u can see changes in main branch, side branch in local repo , remote repo</li>
<li>To merge updates in side branch to main - switch to main branch . </li>
<li>then use the command <i>git merge specify the side branch name.</li>
<li>Hit enter and this opens up Vim which is a text editor and this allows you to add a merge message if</li>
<li>you wish or u can do :q! to save and quit  </li>
<li>now if you can zoom in to network graph and get rid of the tag, then you can see this is the process that we've gone through.</li>
<li>if you want to create a new branch AND check it out at the same time, you can simply type <i>git checkout -b [yourbranchname]</i>.</li>
  </section>


 
