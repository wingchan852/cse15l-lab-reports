# **Week 8 Lab Report 5**

`grade.sh`

```
# Create your grading script here
set -e
CPATH=".:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar"
rm -rf student-submission
git clone $1 student-submission

# check file exist
if [[ -f "./student-submission/ListExamples.java" ]]
then
    echo "correct file submitted"
else
    echo "missing file"
fi

# copy the test & lib to student-submission
cp TestListExamples.java ./student-submission/
cp -r lib ./student-submission/
set +e
# compile the test & student code
cd student-submission
javac -cp $CPATH *.java
java -cp $CPATH org.junit.runner.JUnitCore TestListExamples 1> stdout

CHECK=$(grep -o "Failures" stdout)
PASS=$(grep -E -o ".{0,2}test.{0,0}" stdout)
FAILURE=$(grep -E -o "Failures.{0,3}" stdout)

# check how many passed tests
if [[ $CHECK ]]
    then
        echo "Total: 4 tests"
        grep "Failures" stdout
    else
        echo "Total: 4 tests"
        echo "You pass: $PASS"
fi
```

1. URL:
   https://github.com/ucsd-cse15l-f22/list-methods-lab3
   ![image](lab5-images/initial.png)
2. URL:
   https://github.com/ucsd-cse15l-f22/list-methods-corrected
   ![image](lab5-images/correct.png)
3. URL:
   https://github.com/ucsd-cse15l-f22/list-methods-compile-error
   ![image](lab5-images/error.png)

Using #2 as an example:

## **Step 1**:

Clone the repository `https://github.com/ucsd-cse15l-f22/list-methods-corrected`

## **Step 2**:

Check if the folder `student-submission` exists. In this case, it returns `true` and print the message `"correct file submitted"`.

## **Step 3**:

copy `TestListExamples.java` and `lib`(contain JUnit files) into `student-submission` folder. Then we `set +e` to allow error happen.

## **Step 4**:

Get into the `student-submission` folder and compile & run the JUnit

```
CPATH=".:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar"
```

and

```
javac -cp $CPATH *.java
java -cp $CPATH org.junit.runner.JUnitCore TestListExamples 1> stdout
```

Redirect the stdoutput to the file called `stdout`

## **Step 5**:

Run the following commands:

```
CHECK=$(grep -o "Failures" stdout)
```

Search the word `"Failures"` if it exist in file `stdout`. In this case, it will return `false` so `CHECK = false`

```
PASS=$(grep -E -o ".{0,2}test.{0,0}" stdout)
```

Search the word `"test"` in file `stdout` and store its two previous characters + itself in `PASS`. It counts the numbers of passing test. In this case, `PASS = 4 test`

```
FAILURE=$(grep -E -o "Failures.{0,3}" stdout)
```

Search the word `"Failures"` in file stdout and store 2 character after `"Failures"` + itself in `FAILURE`. It counts the numbers of failing test. In this case, `FAILURE = false` because it passes all the tests so `"Failures"` does not exist in `stdout`.

## **Step 6**:

Use `CHECK` to check if the function whether pass all tests or not. In this case, `CHECK` is `false` so it goes to the `else statement`. It then prints out `"Total: 4 tests"` and `"You pass: $PASS"` where `PASS = 4`

[Return to the main page](index.md)
