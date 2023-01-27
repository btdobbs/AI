# Project 0 - Submitting Projects

## Introduction

The projects for this class assume you use Python 3.6.

Project 0 will cover the following:

* Instructions on how to set up the right Python version
* Workflow examples
* A mini-Python tutorial
* Project grading: Every project’s release includes its autograder for you to run yourself

### Files to Edit and Submit

You will fill in portions of addition.py , buyLotsOfFruit.py , and shopSmart.py. Please do not change the other files in this repository or add new files to your repository. Submit project as py file(s) via Moodle. The due dates for projects are listed on the syllabus. No late project will be accepted without a starfish notice.

### Evaluation

Your code will be autograded for technical correctness. Please do not change the names of any provided functions or classes within the code, or you will wreak havoc on the autograder. The correctness of your implementation will be the final judge of your score. If necessary, a review and grade of assignments will be completed individually to ensure that you receive due credit for your work.  Your lowest project grade will be dropped.

### Academic Dishonesty and Getting Help

Please follow the [50 foot Policy](https://www.dna.caltech.edu/courses/cs191/50ft_policy.pdf) when collaborating on projects.

## Python Installation

Many of you will not have Python 3.6 already installed on your computers. [Conda](https://docs.conda.io/en/latest/) is an easy way to manage many different environments, each with its own Python versions and dependencies. This allows one to avoid conflicts between our preferred Python version and that of other classes. We’ll walk through how to set up and use a conda environment.

On Windows, to execute these commands, you need to be in an Anaconda prompt.

Prerequisite: [Anaconda](https://docs.anaconda.com/anaconda/install/)

### Creating a Conda Environment

The command for creating a conda environment with Python 3.6 is:

```sh
conda create --name <env-name> python=3.6
```

### Entering the Environment

To enter the conda environment that we just created, do the following.

```sh
% conda activate <env-name>
(<env-name>) % python -V
Python 3.6.6 :: Anaconda, Inc.
```

The Python version within the environment should be 3.6. The tag ( <env-name> ) shows you the name of the conda environment that is active.

### Leaving the Environment

Leaving the environment is just as easy.

```sh
(<env-name>) % conda deactivate
% python -V
Python 3.9.10 :: Anaconda custom (x86_64)
```

Our python version has now returned to whatever the system default is.

## Workflow/ Setup Examples

You are not expected to use a particular code editor. Here are some suggestions on convenient workflows.

### [IDE](https://github.com/btdobbs/COSC-440/blob/main/Project/IDE.md)

You are highly encouraged to read the Using an IDE section if using an IDE to learn convenient features.


### [Terminal](https://github.com/btdobbs/COSC-440/blob/main/Project/Terminal.md)

Using Unix and Windows CLI (Command Line Interface) is useful to be able to edit code on any machine without setup and remote connecting setups.

## Python Basics

If you’re new to Python or need a refresher, we recommend going through the [Python basics tutorial](https://github.com/btdobbs/COSC-440/blob/main/Project/Python.md).

## Autograding

To get you familiarized with the autograder, you will code, test, and submit python files solving three questions.

You can download all of the files associated with this course as a zip archive from main github repository via the Code button.  Unzip the <course>.zip file and examine its contents:

```sh
% unzip <course>.zip
% cd <course>/Project/00/
% ls
addition.py
autograder.py
buyLotsOfFruit.py
grading.py
projectParams.py
shop.py
shopSmart.py
testClasses.py
testParser.py
test_cases
tutorialTestClasses.py
```

This contains a number of files you’ll edit or run:
* addition.py : source file for question 1
* buyLotsOfFruit.py : source file for question 2
* shop.py : source file for question 3
* shopSmart.py : source file for question 3
* autograder.py : autograding script

and others you can ignore:
* test_cases : directory contains the test cases for each question
* grading.py : autograder code
* testClasses.py : autograder code
* tutorialTestClasses.py : test classes for this particular project
* projectParams.py : project parameters

The following command grades your solution to all three problems.

```sh
python autograder.py
```

If we run it before editing any files we get a page or two of output:

```sh
% python autograder.py
Starting on 1-21 at 23:39:51
Question q1
===========
*** FAIL: test_cases/q1/addition1.test
***     add(a, b) must return the sum of a and b
***     student result: "0"
***     correct result: "2"
*** FAIL: test_cases/q1/addition2.test
***     add(a, b) must return the sum of a and b
***     student result: "0"
***     correct result: "5"
*** FAIL: test_cases/q1/addition3.test
***     add(a, b) must return the sum of a and b
***     student result: "0"
***     correct result: "7.9"
*** Tests failed.
### Question q1: 0/1 ###
Question q2
===========
*** FAIL: test_cases/q2/food_price1.test
***     buyLotsOfFruit must compute the correct cost of the order
***     student result: "0.0"
***     correct result: "12.25"
*** FAIL: test_cases/q2/food_price2.test
***     buyLotsOfFruit must compute the correct cost of the order
***     student result: "0.0"
***     correct result: "14.75"
*** FAIL: test_cases/q2/food_price3.test
***     buyLotsOfFruit must compute the correct cost of the order
***     student result: "0.0"
***     correct result: "6.4375"
*** Tests failed.
### Question q2: 0/1 ###
Question q3
===========
Welcome to shop1 fruit shop
Welcome to shop2 fruit shop
*** FAIL: test_cases/q3/select_shop1.test
***     shopSmart(order, shops) must select the cheapest shop
***     student result: "None"
***     correct result: "<FruitShop: shop1>"
Welcome to shop1 fruit shop
Welcome to shop2 fruit shop
*** FAIL: test_cases/q3/select_shop2.test
***     shopSmart(order, shops) must select the cheapest shop
***     student result: "None"
***     correct result: "<FruitShop: shop2>"
Welcome to shop1 fruit shop
Welcome to shop2 fruit shop
Welcome to shop3 fruit shop
*** FAIL: test_cases/q3/select_shop3.test
***     shopSmart(order, shops) must select the cheapest shop
***     student result: "None"
***     correct result: "<FruitShop: shop3>"
*** Tests failed.
### Question q3: 0/1 ###
Finished at 23:39:51
Provisional grades
==================
Question q1: 0/1
Question q2: 0/1
Question q3: 0/1
------------------
Total: 0/3
Your grades are NOT yet registered.  To register your grades, make sure
to follow your instructor's guidelines to receive credit on your project.
```

For each of the three questions, this shows the results of that question’s tests, the questions grade, and a final summary at the end. Because you haven’t yet solved the questions, all the tests fail. As you solve each question you may find some tests pass while other fail. When all tests pass for a question, you get full marks. Looking at the results for question 1, you can see that it has failed three tests with the error message “add(a, b) must return the sum of a and b”. The answer your code gives is always 0, but the correct answer is different. We’ll fix that in the next tab.

## Q1: Addition

Open addition.py and look at the definition of add :

```python
def add(a, b):
    "Return the sum of a and b"
    "*** YOUR CODE HERE ***"
    return 0
```

The tests called this with a and b set to different values, but the code always returned zero. Modify this definition to read:

```python
def add(a, b):
    "Return the sum of a and b"
    print("Passed a = %s and b = %s, returning a + b = %s" % (a, b, a + b))
    return a + b
```

Now rerun the autograder (omitting the results for questions 2 and 3):

```sh
% python autograder.py -q q1
Starting on 1-22 at 23:12:08
Question q1
===========
 *** PASS: test_cases/q1/addition1.test
 ***     add(a,b) returns the sum of a and b
 *** PASS: test_cases/q1/addition2.test
 ***     add(a,b) returns the sum of a and b
 *** PASS: test_cases/q1/addition3.test
 ***     add(a,b) returns the sum of a and b
 ### Question q1: 1/1 ###
 Finished at 23:12:08
 Provisional grades
 ==================
 Question q1: 1/1
 ------------------
Total: 1/1
```

You now pass all tests, getting full marks for question 1. Notice the new lines “Passed a=...” which appear before “*** PASS: ...”. These are produced by the print statement in add . You can use print statements like that to output information useful for debugging.

## Q2: buyLotsOfFruit function

Implement the buyLotsOfFruit(orderList) function in buyLotsOfFruit.py which takes a list of (fruit,numPounds) tuples and returns the cost of your list. If there is some fruit in the list which doesn’t appear in fruitPrices it should print an error message and return None . Please do not change the fruitPrices variable.

Run python autograder.py until question 2 passes all tests and you get full marks. Each test will confirm that buyLotsOfFruit(orderList) returns the correct answer given various possible inputs. For example, test_cases/q2/food_price1.test tests whether:

```python
Cost of [('apples', 2.0), ('pears', 3.0), ('limes', 4.0)] is 12.25
```

## Q3: shopSmart function

Fill in the function shopSmart(orderList,fruitShops) in shopSmart.py , which takes an orderList (like the kind passed in to FruitShop.getPriceOfOrder ) and a list of FruitShop and returns the FruitShop where your order costs the least amount in total. Don’t change the file name or variable names, please. Note that we will provide the shop.py implementation as a “support” file, so you don’t need to submit yours.

Run python autograder.py until question 3 passes all tests and you get full marks. Each test will confirm that shopSmart(orderList,fruitShops) returns the correct answer given various possible inputs. For example, with the following variable definitions:

```python
orders1 = [('apples', 1.0), ('oranges', 3.0)]
orders2 = [('apples', 3.0)]
dir1 = {'apples': 2.0, 'oranges': 1.0}
shop1 =  shop.FruitShop('shop1',dir1)
dir2 = {'apples': 1.0, 'oranges': 5.0}
shop2 = shop.FruitShop('shop2', dir2)
shops = [shop1, shop2]
```

test_cases/q3/select_shop1.test tests whether: shopSmart.shopSmart(orders1, shops) == shop1
and test_cases/q3/select_shop2.test tests whether: shopSmart.shopSmart(orders2, shops) == shop2

## Submission

* addition.py
* buyLotsOfFruit.py
* shopSmart.py
