# Lab Report 4
## Task Competition
### Here are the steps to follow in order to complete the task after starting the timer (steps 4-9):
**Step 4: *Logging Into ieng6***

- [ ] `ssh cse15lwi23atv@ieng6.ucsd.edu <enter>`

*screenshot of that*

Here I am typing this command to log into the ieng6 account via ssh, and I do not need to provide a password as logging in is being handled by pre-generated ssh keys.

**Step 5: *Cloning the forked repository***

- [ ] `git clone <^v><enter>`
- [ ] `cd l<tab><enter>`

*screenshot*

In order to clone the repository I am using the ssh clone link on github, so that I will not need to provide a password for authentication when I want to push commits to the repository later. The authentication here is also being handled by generated ssh keys. I paste the repository link using ctrl-v. Then, I cd into the cloned repository by pressing tab in order to autocomplete `l` into `lab/7`.

**Step 6: *Running JUnit Tests***

- [ ] `<up><up><up><up><up><up><enter>`
- [ ] `<up><up><up><up><up><up><enter>`

*screenshot*

Since I had run the commands for the JUnit tests before, they were in my Bash history, so I was able to press the <up> arrow 6 times to re-use the JUnit commands. The first time to compile (which is `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`, and the second time to run the tests (this command `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore`). The output of running that last command then shows that a test failed.
  
**Step 7: *Fix the code***
  
- [ ] `nano L<tab>.j<tab><enter>`
- [ ] `<^W><^T>43, 13<enter><backspace>2<^O><enter><^X>`
  
*screenshots*
  
The first thing I do is type `nano` and then use autocomplete to type out the name of the file I want to edit, which is `ListExamples.java`. After running that command and opening nano, I use the search feature in nano by pressing ctrl-w, and then pressing ctrl-t to search by line and column number, which I know before hand is `43, 13`. Then, I edit `index1` to `index2` replacing the `1` with a `2`, and then I save and exit using ctrl-o, pressing enter, and ctrl-x in nano.
  
**Step 8: *Run the JUnit tests again***

- [ ] `<up><up><up><enter>`
- [ ] `<up><up><up><enter>`

*screenshot*
  
Since the JUnit commands were recently used in my Bash History, it took fewer presses of the up arrow key to get to them, and from there I simply run each of the two commands to see that the tests now pass correctly.
  
