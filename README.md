# Python Grader

This script clones multiple students' assignments from a git server, runs tests on them, and generates a series of good/bad reports to indicate whether the student passed all of the tests. For students that did
not pass all of the tests, a report will be generated that provides all test output.

This script is provided for educational purposes and does not necessarily demonstrate best engineering practices, etc.

## Use

Suppose you have:
  * students:
    * github.com/student1
    * github.com/student2
    * github.com/student3
  * an assignment named echo-server
  * that each student has their own repo:
    * github.com/student1/echo-server
    * etc.
  * that `users.txt` contains the github usernames of your students:
    ```
    student1
    student2
    student3
    ```

Given the above, you would run the script with `python main.py echo-server users.txt`

Successful execution of this script would create the following directories:
  * `reports/echo-server/good`
  * `reports/echo-server/bad`

The good and bad report directories would be populated with the results of the students' tests. Students who failed some tests would have reports in the `bad` directory; students who passed all tests would have reports generated in the `good` directory.

This reporting isn't completely perfect, so if a student shows up in the `bad` directory then you should investigate their code an confirm that they really do have mistakes.

## Security Notice

By running this script you're giving your students arbitrary execution under your user on your machine. It might be wise to run this script under a new user on your machine, or within a virtual machine.
