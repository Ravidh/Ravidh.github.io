# Advanced programming skills - Python

## Class 1

# **Git**

for more information - 
- The git course in teachable
- The slides: Introduction to git, Using git, GitHub 

## How to manage files in the terminal

git status - which files has changed

git diff - what are the changes that were made since the last commit

git add [plan.md](http://plan.md) - mark this file to be in the staging area

git commit -m "update plan" - commit: commit the files, -m: add the message in '_'. 

- It is important to add significant messages that explains what we did in the code before the commit. This helps to keep record on changes also some time after.
- The -m is specific for the programm. Here it is specific for git

git log - shows the record of all the commits and the comments that was added with them.

git show "the shaw of the file after a specific commit" - shows the changes that was added in the commit.

git remote -v - the original location of the project - 

git show HEAD - show the last one that has been used

git push - push out the changes to the git repository

Two main modes of working - 

- Work on your own project
- Dealing with someone else's project - you work on a clone and you won't be able to push put changes, because it is their repository.
    - To make the clone you need to make a fork - a copy of the repository. Then you make a clone of the project.
    - you can push it out to your copied repository, but the other person will not see it.
    - To share it back with the owner you need to pull request - asking the other person to integrate the changes.
        - The other person can decide this is not helpful, reject the request.
        - The other person can ask you to continue develop your idea, and you work on it together.
        - The other person can accept it and add the changes to his own file in his own repository.
    
    < In Gitlab it is called differently. >
    

Test case - see if there is a bag in the program. 

# Testing Demo

How do I verify that my code work?

- check it manually
- automatic way - have another program that will see if the outcome is the expected one

Testing Flask - 

clone the application - 

`git clone https://github.com/pallets/flask.git`

flask is a tool to build applications but it is also an application by itself.

`pip install -r requirements/tests.txt` - will install all the python modules that are needed to test this/my application. 

`pytest`

Have some test and the only thing you need to do is to run this application. 

How do you test your code - 

We need to know what is the expected outcome. 

The point of testing is not to verify that everything work, but to verify that we get what we want to get. 

Testing demo tools - 

Python modules that can be used for testing.

- doctest - A library. Immediately after the def we add documentations - an example of the function

```python
def add(x, y):
    """
    >>> add(2, 2)
    4
    >>> add(3, 3)
    6
    """
    return x * y
```

`$ python -m doctest mymath.py`

 -m: imports the file. 

'doctest' checks if the def function has a documentation and check wether inside there are >>>. If so, it will compare if the results  are as in the documentations. 

 `echo $?` (in linux) 

if the output is 0 - the code succeeded. any other number means it failed. 

 `echo %ERRORLEVEL%` (in windows) 

With doctest you can test only small things. 

- unittest - module in python.
    
    ```python
    import unittest
    import mymath
    
    class TestMath(unittest.TestCase):
        def test_math(self):
    self.assertEqual(mymath.add(2, 2), 4)
    ```
    

Needs to be object oriented. 

- pytest without classes -  A library - more powerful that unittest.
    
    ```python
    import mymath
    
    def test_math():
        assert mymath.add(2, 2) == 4
    
    def test_more_math():
        assert mymath.add(3, 3) == 6
    ```
    
    It is needed to call the functions test_something. 
    
    pytest will keep running and check all the tests even if there are failures. 
    
    - pytest can run doctest and unittest
    
    
[A guide to install ubuntu bash for windows10](https://altis.com.au/installing-ubuntu-bash-for-windows-10/)
 
