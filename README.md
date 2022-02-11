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


 
