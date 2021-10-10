# Standard Operating Procedures for Northeastern Robotics GitHub
This file will outline all of the requirements each collaborator should follow in order to help develop code. Tutorials are also available in order to show how to use git on the command line along with the GitHub Desktop alternative.

## Table of contents
1. [Principle of GitHub and Standard Workflow](#workflow)
2. [Setting Up Git (Command Line)](#cmd_install)
    1. [Cloning a repository](#git-cloning)
    2. [Commiting/Pushing/Merging](#git-pushing)
3. [Setting up GitHub Desktop (Recommended)](#desktop-install)
    1. [Cloning a repository](#desktop-cloning)
    2. [Commiting/Pushing/Merging](#desktop-pushing)
4. [Code Standards](#coding_practices)
    1. [Comments](#comments)
    2. [Classes](#classes)
    3. [Naming Conventions](#naming)
    4. [Using Constants](#constants)
5. [GitHub Standards](#github_practices)
    1. [Creating and Resolving Issues](#issues)
    2. [Naming and Descriptions](#github-naming)
    3. [Pushing Code](github_pushing)

## Principle of GitHub and Standard Workflow<a name = "workflow"/>
GitHub is one of (if not the) most popular code sharing platform in the world. It allows sharing and collaboration of code in an extremely easy way. For the Robotics club, this will allow multiple people to work on code at once which will make it extremely easy to develop in parallel.

The standard workflow for GitHub can be seen below:
1. Clone repository
2. Pull/Fetch repository
3. Make changes
4. Commit changes
5. Push changes
6. Merge changes

The first step is cloning a repository. This is simply GitHubs way of downloading code from a repository and making it so git (command line interface) or GitHub Desktop (Desktop interface) can track changes.

The second step, Pull/Fetch, is to make sure your local repository is up to date with the latest code. Using Pull will download all the changes and merge them with your local directory. Fetch will download changes without changing local files. For the most part, you will only need to Pull.

The next step is making changes. This is the actual coding! Note, you should always be Pulling and keeping your local repository as up to date as possible. Since you will likely not be working on the same files as other people, this should not be a problem. Always back up your local changes to be safe.

Commiting, pushing, and merging are the steps in order to get your local code into the latest distribution.

## Setting Up Git (Command Line)<a name="cmd_install"/>
**_NOTE:_** Use either Git or Github Desktop, you do **NOT** need both.
This section is assuming you already have git installed and registered with your credentials. If you have not already, [heres a tutorial.](https://docs.github.com/en/get-started/quickstart/set-up-git)

For a full reference, [click here.](https://git-scm.com/docs)

**Note: You need to be in the repository's local directory for these to work.**
First, to create and edit on your branch, type the following:
```
git checkout -b FirstName-LastName
```
To then switch to that branch, a similar command is used:
```
git checkout FirstName-LastName
```

### Cloning a repository<a name="git-cloning"/>
In order to clone a repository, there are many options. For one (and most likely the easiest), you can get the link to the repository. After "cd"-ing into the desired directory, type
```
git clone https://....  <-replace with your link
```
There are also other options such as downloading and adding, or using SSH, but that should be sufficient. For more information on the other options click [here](https://git-scm.com/docs/git-clone)

### Commiting/Pushing/Merging<a name="git-pushing"/>
In order to the commit, push, and merge the process is slightly more complex than on desktop. First thing to do is to add the changes. Instead of the checkbox interface on desktop, you need to add them in a different way. To add all the files use the following command
```
git add .
```
To read more about git add, read [here.](https://git-scm.com/docs/git-add)

After the files are added, you can then commit the changes
```
git commit -am "Title" -m "Description"
```
To read more, read [here.](https://git-scm.com/docs/git-commit)

To then push type the following command:
```
git push origin FirstName-LastName
```
To read more, read [here.](https://git-scm.com/docs/git-push)

Lastly, to make a pull request. Use the following tutorial as a guide. This will require a browser and GitHub login on browser, but it does not matter what computer you are on since it is all online and changes were commited.
[**Click here**](https://yangsu.github.io/pull-request-tutorial/#:~:text=pull-request-demo-,Creating%20a%20Pull%20Request,-To%20create%20a)

## Setting Up GitHub Desktop (Recomended)<a name="desktop-install"/>
This is how to set up and use GitHub on desktop (available for all operating systems).

Here is what the standard GitHub desktop application looks like:

![GitHub Desktop](https://github.com/Northeastern-Robotics/SOP/blob/main/images/github%20desktop.png?raw=true)

### Cloning a repository<a name="desktop-cloning"/>
In order to clone a repository, and edit files in the first place, you can go File->Clone Repository. If you have already cloned it using the command line, you can add it. Or you can choose a repository in your account/one you have access to. Also, on GitHub's website, there are multiple options to clone, and one of them is through the Desktop application.

After cloning, you are all set up to begin editing!

### Commiting/Pushing/Merging<a name="desktop-pushing"/>
There are permissions set up in the repository that do not allow you to push to origin. Thus, you must make a branch (Name is First-Last name). To do so, click the "Current Branch" at the top, and choose your branch. Or, make a new branch.

Once you are on your branch, the warning in the bottom left (seen in the screenshot above) should go away. You can see your changes on the left. Make sure to only check what is necessary before commiting. The checkboxes can be seen before each changed file on the left side of the application. In the example shown above, I created a file called test.txt, therefore it shows up as green and the changes to the file are seen in the window on the right.

Note: before doing this, you should make sure to Pull (Repository->Pull or Fetch origin)  to make sure all code is up to date before pushing. 

Once all of your files are selected, type a name and description (click [here](#github_practices) for the rules) and click the "Commit to <branch Name>" button on the bottom left. This will commit your changes to the branch.
    
Lastly, in order to push to your branch, push the button labeled "Push to origin" (in the screenshot it is labeled as "Fetch origin" but after commiting it will change). Lastly, in the middle of the window, a blue button will appear that is labeled "Create Pull Request." This will take you to a browser to once again fill in a name and description. After clicking the green button, "Create Pull Request," your code will be ready for an admin to look at, approve, and merge to the main branch for everyone to use.

## Coding Standards<a name = "coding_practices" />
Since this code will be shared between members, rewritten, and moderated by team leaders. All code that is pushed is expected to follow each guideline presented. Code that does not will not be merged into the main branch.

(Full documentation for conventions for [Python](https://www.python.org/dev/peps/pep-0008/) and [C++](https://google.github.io/styleguide/cppguide.html). Note, mostly everything here and in these are not all exactly required, there is some flexibility. But the goal is to have all code in our repositories being cohesive and understandable)

### Comments<a name = "comments" />
Comments should be concise, easy to read, and explanatory. The expectation is comments should match a level where the reader knows progammming and basic/common concepts, but does not know the specifics of the code being commented. Nearly every line/concept should be commented. Just commenting at the top of functions/classes is not enough.

Here are the [required rules for commenting](https://stackoverflow.blog/2021/07/05/best-practices-for-writing-code-comments/) (click link for more details on each one):
1. Comments should not duplicate the code
2. Good comments do not excuse unclear code
3. If you can't write a clear comment, there may be a problem with the code
4. Comments should dispel confusion, not cause it
5. Explain unidiomatic code in comments
6. Provide links to the original source of copied code
7. Include links to external references where they will be most helpful
8. Add comments when fixing bugs
9. Use comments to mark incomplete implementations

For more in depth and language specific examples, click for the full [Python](https://developer.lsst.io/python/numpydoc.html) and [C++](https://developer.lsst.io/cpp/api-docs.html#documentation-must-be-delimited-in-javadoc-style) commenting guidelines.

### Comments for classes and functions
Here is an example of a well commented function. All functions in pushed code should look like this and follow very similar if not exact formatting. 

<table style='table-layout:fixed'>
<tr>
<th>Python</th>
<th>C++</th>
</tr>
<tr>
<td>

```python
def my_function(p1, p2, p3):
  """my_function does blah blah blah
    Parameters:
      p1 (type): Description of p1
      p2 (type): Description of p2
      p3 (type): Description of p3
    Returns:
      Describe what it will return. Omit if nothing
  """
  
  #Code for the function goes here
```
</td>
<td>

```C++
  /**
   * Description of function
   *
   * @param p1 Description of p1
   * @param p1 Description of p2
   * @param p3 Description of p3
   * @return Describe what to return. If nothing, remove this line
   */
  int my_function(int p1, int p2, int p3)
  {
    //Code for the function goes here
  }
```
</td>
</tr>
</table>

For classes, the structure is similar. Please follow these guidlines when coding classes.

<table style='table-layout:fixed'>
<tr>
<th>Python</th>
<th>C++</th>
</tr>
<tr>
<td>

```python
class Person:
    """
    A class to represent a person.

    ...

    Attributes
    ----------
    name : str
        first name of the person
    surname : str
        family name of the person
    age : int
        age of the person

    Methods
    -------
    info(additional=""):
        Prints the person's name and age.
    """
  
  #Code for the class goes here
```
</td>
<td>

```C++
/**
 * Implementation of a trace facility for LSST
 *
 * Tracing is controlled on a per "component" basis, where a "component" is a
 * name of the form aaa.bbb.ccc where aaa is the Most significant part; for
 * example, the utilities library might be called "utils", the doubly-linked
 * list "utils.dlist", and the code to destroy a list "utils.dlist.del"
 *
 */
class TraceImpl
{
    public:
        ...
}
```
</td>
</tr>
</table>

### Classes<a name = "classes" />

All classes, depending on the language, should have a few basic functions. The required functions for all languages are as follows:
* Default constructor (and destructor if necessary)
* String methods to allow for easy printing/debugging

#### Python

All classes should have as many "magic methods" as possible (https://rszalski.github.io/magicmethods/)
The ones required for classes are the __str__ and __repr__. Both methods are shown in the code example below, and the key reason it to make debugging easier as it prints out a readable format for your class. Here are good examples for a class Person that has a name and age attribute (although comments are omitted here for the sake of brevity, these should be commented):
<table style='table-layout:fixed'>
<tr>
<th>__repr__</th>
<th>__str__</th>
</tr>
<tr>
<td>

```python
  def __repr__():
    return "Person(" + str(name) + ", " + str(age) + ")"
```
</td>
<td>

```Python
  def __str__():
    return "Name: " + str(name) + ", Age: " + str(age) + "\n"
```
</td>
</tr>
</table>

Note the main differences between the __str__ function and the __repr__ function. The str function is supposed to be human readable. This should print out all of the variable states that are deemed relevant in order to get an overview of the current state of that particular object. The __repr__, on the other hand, should be a short string that indicates its class, and as shown above, maybe one or two defining features shown in the parenthesis. This is not neccesary though, but for small classes having that information may deem helpful.

#### C++

C++ classes that are complicated and lengthy should be defined using a header file as well as a cpp file, using #ifndef statements to avoid errors. Smaller classes can skip the header file, but classes must be in their own C++ file along with their operator methods and any other helper methods directly related to the base implementation of the class.

C++ classes should provide an insertion operator as well as a to_string() method. Examples for a class Person, which has a name and age, are shown below:

<table style='table-layout:fixed'>
<tr>
<th>Insertion Operator</th>
<th>to_string</th>
</tr>
<tr>
<td>

```C++
    //Note, this method is NOT inside the class, it is defined outside. (should be declared in .h, implemented in .cpp)
    std::ostream& operator <<(std::ostream& ours, ClassName name)
    {
        return outs << "ClassName("<<name.getProperty()<<")";
    }
```
</td>
<td>

```C++
    //Note how in this example, they use the previously defined << operator to make things simpler.
    //Note, this is NOT inside the class. It is defined outside.
    std::string to_string(ClassName name)
    {
        std::ostringstream ssl
        ss << name;
        return ss.str()
    }
```
</td>
</tr>
</table>

Both of these should be descriptive and say everything necessary that someone might want to print about a class. Make sure not to add newlines or "endl" at the end as that should be left to the user implementing these functions.

### Naming Conventions<a name = "naming" />
Naming conventions are varied depending on where you look and for what language, but for the most part names just need to be clear. For our purposes, the following naming conventions can be followed:

<table style='table-layout:fixed'>
<thead>
  <tr>
    <th></th>
    <th>Convention</th>
    <th>Example</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Classes</td>
    <td>Capitalised and Mixed Case</td>
    <td>RobotDog</td>
  </tr>
  <tr>
    <td>Functions</td>
    <td>Lowercase and mixed case, formatted as a question/command</td>
    <td>isEqual(), getProperty()</td>
  </tr>
  <tr>
    <td>Variables</td>
    <td>Lowercase with underscores in between words. No numbers of special characters (other than underscores). <br>Should be as descriptive as possible. <br>The one exception is looping variables (such as i, x, j, etc) where the sole purpose is for a loop iterator.</td>
    <td>maxmimum_value, robot_dog</td>
  </tr>
  <tr>
    <td>Constants</td>
    <td>All capital letters with underscores</td>
    <td>PI, TOTAL_VALUE</td>
  </tr>
  <tr>
    <td>File names</td>
    <td>lowercase and Mixed Case</td>
    <td>helperFile.py</td>
  </tr>
</tbody>
</table>
    
    
### Using Constants<a name = "constants" />
It is an inevitavility that physical constants will play a role in the creation of a lot of physical project. But, this is no excuse to litter files with constants. The issue arises where a constant needs to be changed and it cannot be located. This is why all constants should follow a few basic rules. First, they should all be in caps, and they should also be located in a separate file. Extremely descript names are needed as well as comments explaining **__exactly__** what they do and what file they are used in are required. Each module that uses constants should share one constants file. If a module has both C++ and python code, it acceptable to use two separate files.

For python, constants should be located in a file with the name "\<module\>\_constants.py"
Here is an example of a constants file for Python and C++

<table style='table-layout:fixed'>
<tr>
<th>TestModule_constants.py</th>
<th>TestModule_constants.h</th>
</tr>
<tr>
<td>

```python
PI = 3.14 #This is used in file math.py and is the value of the mathematical symbol "pi"
GRAVITATIONAL_ACCELERATION = 9.8 #This is used in physics.py and is the constant for acceleration due to gravity on earth. 
                                 #Use multiple lines and be sure to describe exactly what it is doing
```
</td>
<td>

```C++
#ifndef TEST_MODULE_CONSTANTS_H //Use this so symbols are not defined multiple times
#define TEST_MODULE_CONSTANTS_H

const double PI = 3.14; //This is used in file math.cpp and is the value of the mathematical symbol "pi"
const double GRAVITATIONAL_ACCELERATION = 9.8 //This is used in physics.cpp and is the constant for acceleration due to gravity on earth. 
                                              //Use multiple lines and be sure to describe exactly what it is doing'

#endif
```
</td>
</tr>
</table>

Then, here is how to use it. (Assuming constants file is in the same directory as the file you are working in)

<table style='table-layout:fixed'>
<tr>
<th>otherFile.py</th>
<th>otherFile.cpp</th>
</tr>
<tr>
<td>

```python
import TestModule_constants.py as constants

#Other code here....
    
x = 2 * constants.PI * radius
    
#Continue code
```
</td>
<td>

```C++
#include "Test_Module.h"

 //Other code
    
    x = 2 * PI * radius;

//Continue code
```
</td>
</tr>
</table>


## GitHub Standards<a name = "github_practices" />
These are the basic standards that everyone on GitHub is expected to follow. If they are not followed by both admin and members, they risk losing access to the GitHub.

### Creating and Resolving Issues<a name = "issues" />
It may come to the point where there will be issues in the code that need resolving. In this case, it is always acceptable (and encouraged) to use the Issues feature in GitHub. In order to create an Issue (which is essentially a bug report), after going to the repository on Github.com, you can click the "Issues" tab at the top and then create a new issue and describe it. 
    
Then, in pull requests you can link it to an issue if that particular request is what is being solved.
    
For a tutorial on creating issues: [Click here.](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-an-issue)
For a tutorial on linking a pull request to an issue [Click here.](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue)
    
### Naming and Descriptions<a name = "github-naming" />
When commiting code and putting in pull requests, these are the naming and description standards you should follow.

The name, although auto-filled, should be changed to describe exactly what task you are doing. Such as if you changed RobotLeg.py, you should say "Edited Leg Functionality."
    
The description is where you should go in depth about exactly what was changed. Nearly every change should be explained so that the admin that will review your code has a general idea of what is going on. It should also be noted if there are parts missing or some special circuimstances that would make merging difficult.
    
### Pushing Code<a name = "github_pushing" />
By default, code cannot be pushed to the main branch. A branch should be made with your first and last name that will be the branch you exclusively use. (ex: Bob-Smith).
    
Code that is being pushed should also follow all conventions as described inside this document. Even if something is not explicitly said here, code should be as neat and organized as possible. Code should also be complete. Files with unimplemented features should be avoided. Since it may sometimes be necessary to share code that is not yet fully implmented, it should be made clear in the code (through comments and raising errors) that that section is not fully implemented. 
    
All pushed code will be reviewed by admin so it is up to their judgment if the code fits the criteria. Note, admin should hold all code to high standards and there should be no exceptions.
    
For Admins: Read [this for expectations](http://gist.github.com/mikepea/863f63d6e37281e329f8)
 
