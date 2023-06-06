# Debugging Sceneario

After finishing my grader implementaion for lab 6 and running the grade.sh script, i expected it to work perfectly.
However that is not the case and instead i have errors!

I am using windows 11,
and this was the command i entered: 
```
bash grade.sh  https://github.com/ucsd-cse15l-f22/list-methods-lab3
```

Here is the output i got:
```
Finished cloning
ListExample.java found
Compilation Succeeded
Error: Could not find or load main class org.junit.runner.JUnitCore
Caused by: java.lang.ClassNotFoundException: org.junit.runner.JUnitCore
SUCCESS 4/4!
```

Here is the code for my grade.sh script:

```
CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'

if [[ -d student-submission ]]
then
    rm -rf student-submission
fi

if [[ -d grading-area ]]
then
    rm -rf grading-area
fi

mkdir grading-area

git clone $1 student-submission
echo 'Finished cloning'

if [[ -f "student-submission/ListExamples.java" ]]
then
        echo 'ListExample.java found'
else
        echo 'ListExamples.java NOT found!'
        echo 'Score: 0/4!'
        exit 1
fi


cp student-submission/ListExamples.java ./grading-area

cd grading-area

javac -cp $CPATH *.java

if [[ $? -eq 0 ]]
thenline 
        echo 'Compilation Succeeded'
else
        echo 'Compilation FAILED!'
        echo 'Score: 0/4!'
        exit 1
fi


java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > junit-output.txt

FAILURES=$(grep -c 'FAILURES' junit-output.txt)

if [[ $FAILURES -eq 0 ]]
then
    echo 'SUCCESS 4/4!'
    exit 0
else
    echo 'You have FAILURES $FAILURES/4!'
    exit 1
fi
```
I am not sure what is causing this error since i am providing the correct class path.

## Response from TA:
It seems like your issue is that your grading script cannot find the classpath because it is searching for it inside the local directory grading-area.
remove the line: ```cd grading-area```, then replace the line: ```javac -cp $CPATH *.java``` with: ```javac -cp $CPATH grading-area/*.java```

## Student Response to TA:
I have made the exact changes you have suggest and i am getting the same exact error and output!

## Conclusion:
In order to replicate this error it is first important that the right file structure is used,
here is what the file structure for my error looks like: 


<img width="142" alt="image" src="https://github.com/JojoT97/cse15l-lab-reports/assets/130265120/c1a9be82-f070-4c9d-97b7-c7e709bfdb7f">

the "grading-area" and "lib" sub directories are especially important.

The final step that was missing in order to fix the students bug was to replace the first line of code: ```CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'``` with: ```CPATH='.;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar'```
since the students was using a windows operating system, it is neccesary that the student uses the windows syntax for the class path.

