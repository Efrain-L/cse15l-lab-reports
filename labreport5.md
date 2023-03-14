# Lab Report 5
## Revisiting Lab Report 4
### Completing the tasks using a script

For this lab report, I decided to revisit the fourth Lab report, in which we were given tasks to complete as fast as possible. Instead of writing/entering commands manually, I have written a bash script that will complete the tasks in seconds.

The script I wrote is called `task.sh` and contains the following shell commands:
```sh
rm -rf lab7/
git clone $1
cd lab7/
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
sed -i '43 s/index1/index2/' ListExamples.java
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
git add *
git commit -m "SCRIPTED"
git push
```

Going through the script one command at a time, starting with the first line:
* `rm -rf lab7/` This command will 
