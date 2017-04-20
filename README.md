# ReferenceMonitor-Repy

1. Created a reference monitor that will, when asked to do so, protect files starting with private_ (and only those files). If the contents of a file begin with the characters “INV”, then a listfiles() call must not show that the file exists. If the contents of a file begin with the characters “PER” then a removefile() call must raise a RepyArgumentError. In cases not specified above, all calls work identically to the RepyV2 API.

Three design paradigms are at work in this assignment: accuracy, efficiency, and security.

Accuracy: The reference monitor you create should only stop the specified actions from being executed. All other actions should be allowed. For example, if a user tries to open or remove an invisible file, this should be allowed. If a user tries to delete a file “foo” that starts with the characters “PER” this is also allowed (since the file name does not start with private_).
Efficiency: The reference monitor should use a minimum number of resources, so it does not slow down the system. This means you must not re-read the header of each private_ file every time there is a listfiles() or removefile() call. You will need to track the state of the files as the system operates, including the data that is written to files.
Security: The attacker should not be able to circumvent the reference monitor and cause files that should not be displayed to be displayed or files that should not be removed to be removed.


2. Created attack programs that test the following design paradigms at work in reference monitor:

Accuracy: The reference monitor you create should only stop the specified actions from being executed. All other actions should be allowed. For example, if a user tries to open or remove an invisible file, this should be allowed. If a user tries to delete a file “foo” that starts with the characters “PER” this is also allowed (since the file name does not start with private_).
Security: You should not be able to circumvent the reference monitor and cause files that should not be displayed to be displayed or files that should not be removed to be removed.

How to run your tests on many reference monitors:

If you are using Mac or Linux, you can do something like the following:

Put all security layer and attack cases in the same directory you were using before to run single security layer and attack program.

Then you can type the following in the bash shell to execute the testcases with the reference monitors:

for referencemonitor in reference_; do for testcase in netid_.r2py; do python repy.py restrictions.default encasementlib.r2py $referencemonitor $testcase; done; done

All the instructions are mentioned here https://seattle.poly.edu/wiki/EducationalAssignments/ProtectFilePartTwo
