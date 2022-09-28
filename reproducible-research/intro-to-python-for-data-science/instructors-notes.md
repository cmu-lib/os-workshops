---
title: "Running and Quitting"
teaching: 15
exercises: 0
questions:
- "How can I run Python programs?"
objectives:
- "Launch the JupyterLab server." 
- "Create a new Python script." 
- "Create a Jupyter notebook."
- "Shutdown the JupyterLab server."
- "Understand the difference between a Python script and a Jupyter notebook."
- "Create Markdown cells in a notebook."
- "Create and run Python cells in a notebook."
keypoints:
- "Python scripts are plain text files."
- "Use the Jupyter Notebook for editing and running Python."
- "The Notebook has Command and Edit modes."
- "Use the keyboard and mouse to select and edit cells."
- "The Notebook will turn Markdown into pretty-printed documentation."
- "Markdown does most of what HTML does."
---

Many software developers will often use an integrated development environment (IDE) or a 
text editor to create and edit their Python programs which can be executed through the IDE or command line directly. While this is a common approach, we are going to use the [Jupyter Notebook][jupyter] via [JupyterLab][jupyterlab] for the remainder of this workshop.

This has several advantages:
  *   You can easily type, edit, and copy and paste blocks of code.
  *   Tab complete allows you to easily access the names of things you are using
      and learn more about them.
  *   It allows you to annotate your code with links, different sized text, bullets, etc.
      to make it more accessible to you and your collaborators.
  *   It allows you to display figures next to the code that produces them
      to tell a complete story of the analysis.

Each notebook contains one or more cells that contain code, text, or images.

## Getting Started with JupyterLab

JupyterLab is an application with a web-based user interface from [Project Jupyter][jupyter] that 
enables one to work with documents and activities such as Jupyter notebooks, text editors, terminals,
and even custom components in a flexible, integrated, and extensible manner. JupyterLab requires a
reasonably up-to-date browser (ideally a current version of Chrome, Safari, or Firefox); Internet
Explorer versions 9 and below are *not* supported.

JupyterLab is included as part of the Anaconda Python distribution. If you have not already
installed the Anaconda Python distribution, see [the setup instructions]({{ page.root }}{% link
setup.md %})
for installation instructions.

Even though JupyterLab is a web-based application, JupyterLab runs locally on your machine and 
does not require an internet connection.
*   The JupyterLab server sends messages to your web browser.
*   The JupyterLab server does the work and the web browser renders the result.
*   You will type code into the browser and see the result when the web page talks to the 
    JupyterLab server.

> ## JupyterLab? What about Jupyter notebooks?
> 
> JupyterLab is the [next stage in the evolution of the Jupyter Notebook](https://jupyterlab.readthedocs.io/en/stable/getting_started/overview.html#overview).
> If you have prior experience working with Jupyter notebooks, then you will have a good idea of what to expect from JupyterLab. 
> 
> Experienced users of Jupyter notebooks interested in a more detailed discussion of the similarities and differences
> between the JupyterLab and Jupyter notebook user interfaces can find more information in the 
> [JupyterLab user interface documentation][jupyterlab-ui].
{: .callout}

## Starting JupyterLab

You can start the JupyterLab server through the command line or through an application called 
`Anaconda Navigator`. Anaconda Navigator is included as part of the Anaconda Python distribution.

### macOS - Command Line
To start the JupyterLab server you will need to access the command line through the Terminal. 
There are two ways to open Terminal on Mac.

1. In your Applications folder, open Utilities and double-click on Terminal
2. Press <kbd>Command</kbd> + <kbd>spacebar</kbd> to launch Spotlight. Type `Terminal` and then 
double-click the search result or hit <kbd>Enter</kbd>

After you have launched Terminal, type the command to launch the JupyterLab server.

~~~
$ jupyter lab
~~~
{: .bash}

### Windows Users - Command Line
To start the JupyterLab server you will need to access the Anaconda Prompt.

Press <kbd>Windows Logo Key</kbd> and search for `Anaconda Prompt`, click the result or press enter.

After you have launched the Anaconda Prompt, type the command:

~~~
$ jupyter lab
~~~
{: .bash}

###  Anaconda Navigator

To start a JupyterLab server from Anaconda Navigator you must first [start Anaconda Navigator (click for detailed instructions on macOS, Windows, and Linux)](https://docs.anaconda.com/anaconda/navigator/getting-started/#starting-navigator). You can search for Anaconda Navigator via Spotlight on macOS (<kbd>Command</kbd> + <kbd>spacebar</kbd>), the Windows search function (<kbd>Windows Logo Key</kbd>) or opening a terminal shell and executing the `anaconda-navigator` executable from the command line.

After you have launched Anaconda Navigator, click the `Launch` button under JupyterLab. You may need
to scroll down to find it.

Here is a screenshot of an Anaconda Navigator page similar to the one that should open on either macOS
or Windows.

<p align='center'>
  <img alt="Anaconda Navigator landing page" src="../fig/0_anaconda_navigator_landing_page.png" width="750"/>
</p>

And here is a screenshot of a JupyterLab landing page that should be similar to the one that opens in your 
default web browser after starting the JupyterLab server on either macOS or Windows.

<p align='center'>
  <img alt="JupyterLab landing page" src="../fig/0_jupyterlab_landing_page.png" width="750"/>
</p>

## The JupyterLab Interface

JupyterLab has many features found in traditional integrated development environments (IDEs) but 
is focused on providing flexible building blocks for interactive, exploratory computing.

The [JupyterLab Interface](https://jupyterlab.readthedocs.io/en/stable/user/interface.html) 
consists of the Menu Bar, a collapsable Left Side Bar, and the Main Work Area which contains tabs 
of documents and activities.

### Menu Bar

The Menu Bar at the top of JupyterLab has the top-level menus that expose various actions 
available in JupyterLab along with their keyboard shortcuts (where applicable). The following 
menus are included by default.

*   **File:** Actions related to files and directories such as *New*, *Open*, *Close*, *Save*, etc. The *File* menu also includes the *Shut Down* action used to shutdown the JupyterLab server.
*   **Edit:** Actions related to editing documents and other activities such as *Undo*, *Cut*, *Copy*, *Paste*, etc.
*   **View:** Actions that alter the appearance of JupyterLab.
*   **Run:** Actions for running code in different activities such as notebooks and code consoles (discussed below).
*   **Kernel:** Actions for managing kernels. Kernels in Jupyter will be explained in more detail below.
*   **Tabs:** A list of the open documents and activities in the main work area.
*   **Settings:** Common JupyterLab settings can be configured using this menu. There is also an *Advanced Settings Editor* option in the dropdown menu that provides more fine-grained control of JupyterLab settings and configuration options.
*   **Help:** A list of JupyterLab and kernel help links.

> ## Kernels
> The JupyterLab [docs](https://jupyterlab.readthedocs.io/en/stable/user/documents_kernels.html) 
> define kernels as "separate processes started by the server that run your code in different programming languages and environments."
> When we open a Jupyter Notebook, that starts a kernel - a process - that is going to run the code. 
> In this lesson, we'll be using the Jupyter ipython kernel which lets us run Python 3 code interactively.
> 
> Using other Jupyter [kernels for other programming languages](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels) would let us 
> write and execute code in other programming languages in the same JupyterLab interface, like R, Java, Julia, Ruby, JavaScript, Fortran, 
> etc.
> 
{: .callout}

A screenshot of the default Menu Bar is provided below.

<p align='center'>
    <img alt="JupyterLab Menu Bar" src="../fig/0_jupyterlab_menu_bar.png" width="750"/>
</p>

### Left Sidebar

The left sidebar contains a number of commonly used tabs, such as a file browser (showing the 
contents of the directory where the JupyterLab server was launched), a list of running kernels 
and terminals, the command palette, and a list of open tabs in the main work area. A screenshot of 
the default Left Side Bar is provided below.

<p align='center'>
    <img alt="JupyterLab Left Side Bar" src="../fig/0_jupyterlab_left_side_bar.png" width="250"/>
</p>

The left sidebar can be collapsed or expanded by selecting “Show Left Sidebar” in the View menu or 
by clicking on the active sidebar tab.

### Main Work Area

The main work area in JupyterLab enables you to arrange documents (notebooks, text files, etc.) 
and other activities (terminals, code consoles, etc.) into panels of tabs that can be resized or 
subdivided. A screenshot of the default Main Work Area is provided below.

<p align='center'>
    <img alt="JupyterLab Main Work Area" src="../fig/0_jupyterlab_main_work_area.png" width="750"/>
</p>

Drag a tab to the center of a tab panel to move the tab to the panel. Subdivide a tab panel by 
dragging a tab to the left, right, top, or bottom of the panel. The work area has a single current 
activity. The tab for the current activity is marked with a colored top border (blue by default).

## Creating a Python script

*   To start writing a new Python program click the Text File icon under the *Other* header in the Launcher tab of the Main Work Area.
    *   You can also create a new plain text file by selecting the *New -> Text File* from the *File* menu in the Menu Bar.
*   To convert this plain text file to a Python program, select the *Save File As* action from the *File* menu in the Menu Bar and give your new text file a name that ends with the `.py` extension.
    *   The `.py` extension lets everyone (including the operating system) know that this text file is a Python program.
    *   This is convention, not a requirement.

## Creating a Jupyter Notebook

To open a new notebook click the Python 3 icon under the *Notebook* header in the Launcher tab in 
the main work area. You can also create a new notebook by selecting *New -> Notebook* from the *File* menu in the Menu Bar.

Additional notes on Jupyter notebooks.

  *   Notebook files have the extension `.ipynb` to distinguish them from plain-text Python programs.
  *   Notebooks can be exported as Python scripts that can be run from the command line.

Below is a screenshot of a Jupyter notebook running inside JupyterLab. If you are interested in 
more details, then see the [official notebook documentation][jupyterlab-notebook-docs].

<p align='center'>
    <img alt="Example Jupyter Notebook" src="../fig/0_jupyterlab_notebook_screenshot.png" width="750"/>
</p>

> ## How It's Stored
>
> *   The notebook file is stored in a format called JSON.
> *   Just like a webpage, what's saved looks different from what you see in your browser.
> *   But this format allows Jupyter to mix source code, text, and images, all in one file.
{: .callout}

> ## Arranging Documents into Panels of Tabs
>
> In the JupyterLab Main Work Area you can arrange documents into panels of tabs. Here is an 
> example from the [official documentation][jupyterlab].
> 
> <p align='center'>
>    <img alt="Multi-panel JupyterLab" src="../fig/0_multipanel_jupyterlab_screenshot.png" width="750"/>
> </p>
>
> First, create a text file, Python console, and terminal window and arrange them into three 
> panels in the main work area. Next, create a notebook, terminal window, and text file and 
> arrange them into three panels in the main work area. Finally, create your own combination of 
> panels and tabs. What combination of panels and tabs do you think will be most useful for your 
> workflow?
>
> > ## Solution
> >
> > After creating the necessary tabs, you can drag one of the tabs to the center of a panel to 
> > move the tab to the panel; next you can subdivide a tab panel by dragging a tab to the left, 
> > right, top, or bottom of the panel.
> {: .solution}
{: .challenge}

> ## Code vs. Text
>
> Jupyter mixes code and text in different types of blocks, called cells. We often use the term
> "code" to mean "the source code of software written in a language such as Python".
> A "code cell" in a Notebook is a cell that contains software;
> a "text cell" is one that contains ordinary prose written for human beings.
{: .callout}

## The Notebook has Command and Edit modes.

*   If you press <kbd>Esc</kbd> and <kbd>Return</kbd> alternately, the outer border of your code cell will change from gray to blue.
*   These are the **Command** (gray) and **Edit** (blue) modes of your notebook.
*   Command mode allows you to edit notebook-level features, and Edit mode changes the content of cells.
*   When in Command mode (esc/gray),
    *   The <kbd>b</kbd> key will make a new cell below the currently selected cell.
    *   The <kbd>a</kbd> key will make one above.
    *   The <kbd>x</kbd> key will delete the current cell.
    *   The <kbd>z</kbd> key will undo your last cell operation (which could be a deletion, creation, etc).
*   All actions can be done using the menus, but there are lots of keyboard shortcuts to speed things up.

> ## Command Vs. Edit
>
> In the Jupyter notebook page are you currently in Command or Edit mode?  
> Switch between the modes. 
> Use the shortcuts to generate a new cell. 
> Use the shortcuts to delete a cell.
> Use the shortcuts to undo the last cell operation you performed.
>
> > ## Solution
> >
> > Command mode has a grey border and Edit mode has a blue border. 
> > Use <kbd>Esc</kbd> and <kbd>Return</kbd> to switch between modes. 
> > You need to be in Command mode (Press <kbd>Esc</kbd> if your cell is blue).  Type <kbd>b</kbd> or <kbd>a</kbd>.
> > You need to be in Command mode (Press <kbd>Esc</kbd> if your cell is blue).  Type <kbd>x</kbd>.
> > You need to be in Command mode (Press <kbd>Esc</kbd> if your cell is blue).  Type <kbd>z</kbd>.
> {: .solution}
{: .challenge}

### Use the keyboard and mouse to select and edit cells.

*   Pressing the <kbd>Return</kbd> key turns the border blue and engages Edit mode, which allows 
    you to type within the cell.
*   Because we want to be able to write many lines of code in a single cell,
    pressing the <kbd>Return</kbd> key when in Edit mode (blue) moves the cursor to the next line 
    in the cell just like in a text editor.
*   We need some other way to tell the Notebook we want to run what's in the cell.
*   Pressing <kbd>Shift</kbd>+<kbd>Return</kbd> together will execute the contents of the cell.
*   Notice that the <kbd>Return</kbd> and <kbd>Shift</kbd> keys on the right of the keyboard are 
    right next to each other.

### The Notebook will turn Markdown into pretty-printed documentation.

*   Notebooks can also render [Markdown][markdown].
    *   A simple plain-text format for writing lists, links, 
        and other things that might go into a web page.
    *   Equivalently, a subset of HTML that looks like what you'd send in an old-fashioned email.
*   Turn the current cell into a Markdown cell by entering the Command mode (<kbd>Esc</kbd>/gray) 
    and press the <kbd>M</kbd> key.
*   `In [ ]:` will disappear to show it is no longer a code cell and you will be able to write in 
    Markdown.
*   Turn the current cell into a Code cell by entering the Command mode (<kbd>Esc</kbd>/gray) and 
    press the <kbd>y</kbd> key.

### Markdown does most of what HTML does.

<div class="row">
  <div class="col-md-6" markdown="1">
    
~~~
*   Use asterisks
*   to create
*   bullet lists.
~~~

  </div>
  <div class="col-md-6" markdown="1">
  
*   Use asterisks
*   to create
*   bullet lists.

  </div>
</div>

<div class="row">
  <div class="col-md-6" markdown="1">
    
~~~
1.  Use numbers
1.  to create
1.  numbered lists.
~~~

  </div>
  <div class="col-md-6" markdown="1">

1.  Use numbers
1.  to create
1.  numbered lists.

  </div>
</div>

<div class="row">
  <div class="col-md-6" markdown="1">
    
~~~
*  You can use indents
	*  To create sublists 
	*  of the same type
*  Or sublists
	1. Of different
	1. types
~~~

  </div>
  <div class="col-md-6" markdown="1">
  
*  You can use indents
	*  To create sublists
	*  of the same type
*  Or sublists
	1. Of different
	1. types
  
  </div>
</div>

<div class="row">
  <div class="col-md-6" markdown="1">
    
~~~
# A Level-1 Heading
~~~

  </div>
  <div class="col-md-6" markdown="1">
  
# A Level-1 Heading

  </div>
</div>

<div class="row">
  <div class="col-md-6" markdown="1">
    
~~~
## A Level-2 Heading (etc.)
~~~

  </div>
  <div class="col-md-6" markdown="1">
  
## A Level-2 Heading (etc.)

  </div>
</div>

<div class="row">
  <div class="col-md-6" markdown="1">
    
~~~
Line breaks
don't matter.

But blank lines
create new paragraphs.
~~~

  </div>
  <div class="col-md-6" markdown="1">
  
Line breaks
don't matter.

But blank lines
create new paragraphs.

  </div>
</div>

<div class="row">
  <div class="col-md-6" markdown="1">
    
~~~
[Create links](http://software-carpentry.org) with `[...](...)`.
Or use [named links][data_carpentry].

[data_carpentry]: http://datacarpentry.org
~~~

  </div>
  <div class="col-md-6" markdown="1">
  
[Create links](http://software-carpentry.org) with `[...](...)`.
Or use [named links][data_carpentry].

[data_carpentry]: http://datacarpentry.org

  </div>
</div>

> ## Creating Lists in Markdown
>
> Create a nested list in a Markdown cell in a notebook that looks like this:
>
> 1.  Get funding.
> 2.  Do work.
>     *   Design experiment.
>     *   Collect data.
>     *   Analyze.
> 3.  Write up.
> 4.  Publish.
> 
> > ## Solution
> >
> > This challenge integrates both the numbered list and bullet list. 
> > Note that the bullet list is indented 2 spaces so that it is inline with the items of the numbered list.
> > ~~~
> > 1.  Get funding.
> > 2.  Do work.
> >     *   Design experiment.
> >     *   Collect data.
> >     *   Analyze.
> > 3.  Write up.
> > 4.  Publish.
> > ~~~
> {: .solution}
{: .challenge}

> ## More Math
>
> What is displayed when a Python cell in a notebook
> that contains several calculations is executed?
> For example, what happens when this cell is executed?
>
> ~~~
> 7 * 3
> 2 + 1
> ~~~
> {: .language-python}
> 
> > ## Solution
> >
> > Python returns the output of the last calculation.
> > ~~~
> > 3
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Change an Existing Cell from Code to Markdown
>
> What happens if you write some Python in a code cell
> and then you switch it to a Markdown cell?
> For example,
> put the following in a code cell:
>
> ~~~
> x = 6 * 7 + 12
> print(x)
> ~~~
> {: .language-python}
>
> And then run it with <kbd>Shift</kbd>+<kbd>Return</kbd> to be sure that it works as a code cell.
> Now go back to the cell and use <kbd>Esc</kbd> then <kbd>m</kbd> to switch the cell to Markdown
> and "run" it with <kbd>Shift</kbd>+<kbd>Return</kbd>.
> What happened and how might this be useful?
> 
> > ## Solution
> >
> > The Python code gets treated like Markdown text.
> > The lines appear as if they are part of one contiguous paragraph.
> > This could be useful to temporarily turn on and off cells in notebooks that get used for multiple purposes. 
> > ~~~
> > x = 6 * 7 + 12 print(x)
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Equations
>
> Standard Markdown (such as we're using for these notes) won't render equations,
> but the Notebook will.
> Create a new Markdown cell
> and enter the following:
>
> ~~~
> $\sum_{i=1}^{N} 2^{-i} \approx 1$
> ~~~
>
> (It's probably easier to copy and paste.)
> What does it display?
> What do you think the underscore, `_`, circumflex, `^`, and dollar sign, `$`, do?
> 
> > ## Solution
> >
> > The notebook shows the equation as it would be rendered from LaTeX equation syntax.
> > The dollar sign, `$`, is used to tell Markdown that the text in between is a LaTeX equation.
> > If you're not familiar with LaTeX,  underscore, `_`, is used for subscripts and circumflex, `^`, is used for superscripts.
> > A pair of curly braces, `{` and `}`, is used to group text together so that the statement `i=1` becomes the subscript and `N` becomes the superscript.
> > Similarly, `-i` is in curly braces to make the whole statement the superscript for `2`.
> > `\sum` and `\approx` are LaTeX commands for "sum over" and "approximate" symbols. 
> {: .solution}
{: .challenge}

## Closing JupyterLab

*   From the Menu Bar select the "File" menu and then choose "Shut Down" at the bottom of the dropdown menu. You will be prompted to confirm that you wish to shutdown the JupyterLab server (don't forget to save your work!). Click "Shut Down" to shutdown the JupyterLab server.
*   To restart the JupyterLab server you will need to re-run the following command from a shell.

~~~
$ jupyter lab
~~~

> ## Closing JupyterLab
>
> Practice closing and restarting the JupyterLab server.
{: .challenge}

[anaconda]: https://docs.continuum.io/anaconda/install
[jupyterlab]: https://jupyterlab.readthedocs.io/en/stable/
[jupyterlab-ui]: https://jupyterlab.readthedocs.io/en/stable/user/interface.html
[jupyterlab-notebook-docs]: https://jupyterlab.readthedocs.io/en/stable/user/notebook.html
[markdown]: https://en.wikipedia.org/wiki/Markdown

{% include links.md %}

---
title: "Variables and Assignment"
teaching: 10
exercises: 10
questions:
- "How can I store data in programs?"
objectives:
- "Write programs that assign scalar values to variables and perform calculations with those values."
- "Correctly trace value changes in programs that use scalar assignment."
keypoints:
- "Use variables to store values."
- "Use `print` to display values."
- "Variables persist between cells."
- "Variables must be created before they are used."
- "Variables can be used in calculations."
- "Use an index to get a single character from a string."
- "Use a slice to get a substring."
- "Use the built-in function `len` to find the length of a string."
- "Python is case-sensitive."
- "Use meaningful variable names."
---
## Use variables to store values.

*   **Variables** are names for values.
*   In Python the `=` symbol assigns the value on the right to the name on the left.
*   The variable is created when a value is assigned to it.
*   Here, Python assigns an age to a variable `age`
    and a name in quotes to a variable `first_name`.

    ~~~
    age = 42
    first_name = 'Ahmed'
    ~~~
    {: .language-python}

*   Variable names
    * can **only** contain letters, digits, and underscore `_` (typically used to separate words in long variable names)
    * cannot start with a digit
    * are **case sensitive** (age, Age and AGE are three different variables)
*   Variable names that start with underscores like `__alistairs_real_age` have a special meaning
    so we won't do that until we understand the convention.

## Use `print` to display values.

*   Python has a built-in function called `print` that prints things as text.
*   Call the function (i.e., tell Python to run it) by using its name.
*   Provide values to the function (i.e., the things to print) in parentheses.
*   To add a string to the printout, wrap the string in single or double quotes.
*   The values passed to the function are called **arguments**

~~~
print(first_name, 'is', age, 'years old')
~~~
{: .language-python}
~~~
Ahmed is 42 years old
~~~
{: .output}

*   `print` automatically puts a single space between items to separate them.
*   And wraps around to a new line at the end.

## Variables must be created before they are used.

*   If a variable doesn't exist yet, or if the name has been mis-spelled,
    Python reports an error. (Unlike some languages, which "guess" a default value.)

~~~
print(last_name)
~~~
{: .language-python}
~~~
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-1-c1fbb4e96102> in <module>()
----> 1 print(last_name)

NameError: name 'last_name' is not defined
~~~
{: .error}

*   The last line of an error message is usually the most informative.
*   We will look at error messages in detail [later]({{ page.root }}/15-scope/#reading-error-messages).

> ## Variables Persist Between Cells
>
> Be aware that it is the *order* of execution of cells that is important in a Jupyter notebook, not the order
> in which they appear. Python will remember *all* the code that was run previously, including any variables you have
> defined, irrespective of the order in the notebook. Therefore if you define variables lower down the notebook and then
> (re)run cells further up, those defined further down will still be present. As an example, create two cells with the
> following content, in this order:
>
> ~~~
> print(myval)
> ~~~
> {: .language-python}
>
> ~~~
> myval = 1
> ~~~
> {: .language-python}
>
> If you execute this in order, the first cell will give an error. However, if you run the first cell *after* the second
> cell it will print out `1`. To prevent confusion, it can be helpful to use the `Kernel` -> `Restart & Run All` option which
> clears the interpreter and runs everything from a clean slate going top to bottom.
{: .callout}

## Variables can be used in calculations.

*   We can use variables in calculations just as if they were values.
    *   Remember, we assigned the value `42` to `age` a few lines ago.

~~~
age = age + 3
print('Age in three years:', age)
~~~
{: .language-python}
~~~
Age in three years: 45
~~~
{: .output}

## Use an index to get a single character from a string.

*   The characters (individual letters, numbers, and so on) in a string are
    ordered. For example, the string `'AB'` is not the same as `'BA'`. Because of
    this ordering, we can treat the string as a list of characters.
*   Each position in the string (first, second, etc.) is given a number. This
    number is called an **index** or sometimes a subscript.
*   Indices are numbered from 0.
*   Use the position's index in square brackets to get the character at that
    position.

![an illustration of indexing](../fig/2_indexing.svg)

~~~
atom_name = 'helium'
print(atom_name[0])
~~~
{: .language-python}
~~~
h
~~~
{: .output}

## Use a slice to get a substring.

*   A part of a string is called a **substring**. A substring can be as short as a
    single character.
*   An item in a list is called an element. Whenever we treat a string as if it
    were a list, the string's elements are its individual characters.
*   A slice is a part of a string (or, more generally, a part of any list-like thing).
*   We take a slice with the notation `[start:stop]`, where `start` is the integer
    index of the first element we want and `stop` is the integer index of
    the element _just after_ the last element we want.
*   The difference between `stop` and `start` is the slice's length.
*   Taking a slice does not change the contents of the original string. Instead,
    taking a slice returns a copy of part of the original string.

~~~
atom_name = 'sodium'
print(atom_name[0:3])
~~~
{: .language-python}
~~~
sod
~~~
{: .output}

## Use the built-in function `len` to find the length of a string.

~~~
print(len('helium'))
~~~
{: .language-python}
~~~
6
~~~
{: .output}

*   Nested functions are evaluated from the inside out,
     like in mathematics.

## Python is case-sensitive.

*   Python thinks that upper- and lower-case letters are different,
    so `Name` and `name` are different variables.
*   There are conventions for using upper-case letters at the start of variable names so we will use lower-case letters for now.

## Use meaningful variable names.

*   Python doesn't care what you call variables as long as they obey the rules
    (alphanumeric characters and the underscore).

~~~
flabadab = 42
ewr_422_yY = 'Ahmed'
print(ewr_422_yY, 'is', flabadab, 'years old')
~~~
{: .language-python}

*   Use meaningful variable names to help other people understand what the program does.
*   The most important "other person" is your future self.

> ## Swapping Values
>
> Fill the table showing the values of the variables in this program
> *after* each statement is executed.
>
> ~~~
> # Command  # Value of x   # Value of y   # Value of swap #
> x = 1.0    #              #              #               #
> y = 3.0    #              #              #               #
> swap = x   #              #              #               #
> x = y      #              #              #               #
> y = swap   #              #              #               #
> ~~~
> {: .language-python}
> > ## Solution
> >
> > ~~~
> > # Command  # Value of x   # Value of y   # Value of swap #
> > x = 1.0    # 1.0          # not defined  # not defined   #
> > y = 3.0    # 1.0          # 3.0          # not defined   #
> > swap = x   # 1.0          # 3.0          # 1.0           #
> > x = y      # 3.0          # 3.0          # 1.0           #
> > y = swap   # 3.0          # 1.0          # 1.0           #
> > ~~~
> > {: .output}
> >
> > These three lines exchange the values in `x` and `y` using the `swap`
> > variable for temporary storage. This is a fairly common programming idiom.
>{: .solution}
{: .challenge}

> ## Predicting Values
>
> What is the final value of `position` in the program below?
> (Try to predict the value without running the program,
> then check your prediction.)
>
> ~~~
> initial = 'left'
> position = initial
> initial = 'right'
> ~~~
> {: .language-python}
> > ## Solution
> > ~~~
> > print(position)
> > ~~~
> > {: .language-python}
> > ~~~
> > left
> > ~~~
> > {: .output}
> >
> > The `initial` variable is assigned the value `'left'`.
> > In the second line, the `position` variable also receives
> > the string value `'left'`. In third line, the `initial` variable is given the
> > value `'right'`, but the `position` variable retains its string value
> > of `'left'`.
> {: .solution}
{: .challenge}

> ## Challenge
>
> If you assign `a = 123`,
> what happens if you try to get the second digit of `a` via `a[1]`?
>
> > ## Solution
> > Numbers are not strings or sequences and Python will raise an error if you try to perform an index operation on a
> > number. In the [next lesson on types and type conversion]({{ page.root }}/03-types-conversion/#convert-numbers-and-strings)
> > we will learn more about types and how to convert between different types. If you want the Nth digit of a number you
> > can convert it into a string using the `str` built-in function and then perform an index operation on that string.
> >
> > ~~~
> > a = 123
> > print(a[1])
> > ~~~
> > {: .language-python}
> > ~~~
> > TypeError: 'int' object is not subscriptable
> > ~~~
> > {: .error}
> >
> >
> > ~~~
> > a = str(123)
> > print(a[1])
> > ~~~
> > {: .language-python}
> > ~~~
> > 2
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

> ## Choosing a Name
>
> Which is a better variable name, `m`, `min`, or `minutes`?
> Why?
> Hint: think about which code you would rather inherit
> from someone who is leaving the lab:
>
> 1. `ts = m * 60 + s`
> 2. `tot_sec = min * 60 + sec`
> 3. `total_seconds = minutes * 60 + seconds`
>
> > ## Solution
> >
> > `minutes` is better because `min` might mean something like "minimum"
> > (and actually is an existing built-in function in Python that we will cover later).
> {: .solution}
{: .challenge}

> ## Slicing practice
>
> What does the following program print?
>
> ~~~
> atom_name = 'carbon'
> print('atom_name[1:3] is:', atom_name[1:3])
> ~~~
> {: .language-python}
>
> > ## Solution
> >
> > ~~~
> > atom_name[1:3] is: ar
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

> ## Slicing concepts
>
> Given the following string:
>
> ~~~
> species_name = "Acacia buxifolia"
> ~~~
> {: .language-python}
>
> What would these expressions return?
>
> 1.  `species_name[2:8]`
> 2.  `species_name[11:]` (without a value after the colon)
> 3.  `species_name[:4]` (without a value before the colon)
> 4.  `species_name[:]` (just a colon)
> 5.  `species_name[11:-3]`
> 6.  `species_name[-5:-3]`
> 7.  What happens when you choose a `stop` value which is out of range? (i.e., try `species_name[0:20]` or `species_name[:103]`)
>
> > ## Solutions
> >
> > 1.  `species_name[2:8]` returns the substring `'acia b'`
> > 2.  `species_name[11:]` returns the substring `'folia'`, from position 11 until the end
> > 3.  `species_name[:4]` returns the substring `'Acac'`, from the start up to but not including position 4
> > 4.  `species_name[:]` returns the entire string `'Acacia buxifolia'`
> > 5.  `species_name[11:-3]` returns the substring `'fo'`, from the 11th position to the third last position
> > 6.  `species_name[-5:-3]` also returns the substring `'fo'`, from the fifth last position to the third last
> > 7.  If a part of the slice is out of range, the operation does not fail. `species_name[0:20]` gives the same result as `species_name[0:]`, and `species_name[:103]` gives the same result as `species_name[:]`
> {: .solution}
{: .challenge}

---
title: "Data Types and Type Conversion"
teaching: 10
exercises: 10
questions:
- "What kinds of data do programs store?"
- "How can I convert one type to another?"
objectives:
- "Explain key differences between integers and floating point numbers."
- "Explain key differences between numbers and character strings."
- "Use built-in functions to convert between integers, floating point numbers, and strings."
keypoints:
- "Every value has a type."
- "Use the built-in function `type` to find the type of a value."
- "Types control what operations can be done on values."
- "Strings can be added and multiplied."
- "Strings have a length (but numbers don't)."
- "Must convert numbers to strings or vice versa when operating on them."
- "Can mix integers and floats freely in operations."
- "Variables only change value when something is assigned to them."
---
## Every value has a type.

*   Every value in a program has a specific type.
*   Integer (`int`): represents positive or negative whole numbers like 3 or -512.
*   Floating point number (`float`): represents real numbers like 3.14159 or -2.5.
*   Character string (usually called "string", `str`): text.
    *   Written in either single quotes or double quotes (as long as they match).
    *   The quote marks aren't printed when the string is displayed.

## Use the built-in function `type` to find the type of a value.

*   Use the built-in function `type` to find out what type a value has.
*   Works on variables as well.
    *   But remember: the *value* has the type --- the *variable* is just a label.

~~~
print(type(52))
~~~
{: .language-python}
~~~
<class 'int'>
~~~
{: .output}

~~~
fitness = 'average'
print(type(fitness))
~~~
{: .language-python}
~~~
<class 'str'>
~~~
{: .output}

## Types control what operations (or methods) can be performed on a given value.

*   A value's type determines what the program can do to it.

~~~
print(5 - 3)
~~~
{: .language-python}
~~~
2
~~~
{: .output}

~~~
print('hello' - 'h')
~~~
{: .language-python}
~~~
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-2-67f5626a1e07> in <module>()
----> 1 print('hello' - 'h')

TypeError: unsupported operand type(s) for -: 'str' and 'str'
~~~
{: .error}

## You can use the "+" and "*" operators on strings.

*   "Adding" character strings concatenates them.

~~~
full_name = 'Ahmed' + ' ' + 'Walsh'
print(full_name)
~~~
{: .language-python}
~~~
Ahmed Walsh
~~~
{: .output}

*   Multiplying a character string by an integer _N_ creates a new string that consists of that character string repeated  _N_ times.
    *   Since multiplication is repeated addition.

~~~
separator = '=' * 10
print(separator)
~~~
{: .language-python}
~~~
==========
~~~
{: .output}

## Strings have a length (but numbers don't).

*   The built-in function `len` counts the number of characters in a string.

~~~
print(len(full_name))
~~~
{: .language-python}
~~~
11
~~~
{: .output}

*   But numbers don't have a length (not even zero).

~~~
print(len(52))
~~~
{: .language-python}
~~~
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-3-f769e8e8097d> in <module>()
----> 1 print(len(52))

TypeError: object of type 'int' has no len()
~~~
{: .error}

## <a name='convert-numbers-and-strings'></a> Must convert numbers to strings or vice versa when operating on them.

*   Cannot add numbers and strings.

~~~
print(1 + '2')
~~~
{: .language-python}
~~~
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-4-fe4f54a023c6> in <module>()
----> 1 print(1 + '2')

TypeError: unsupported operand type(s) for +: 'int' and 'str'
~~~
{: .error}

*   Not allowed because it's ambiguous: should `1 + '2'` be `3` or `'12'`?
*   Some types can be converted to other types by using the type name as a function.

~~~
print(1 + int('2'))
print(str(1) + '2')
~~~
{: .language-python}
~~~
3
12
~~~
{: .output}

## Can mix integers and floats freely in operations.

*   Integers and floating-point numbers can be mixed in arithmetic.
    *   Python 3 automatically converts integers to floats as needed.

~~~
print('half is', 1 / 2.0)
print('three squared is', 3.0 ** 2)
~~~
{: .language-python}
~~~
half is 0.5
three squared is 9.0
~~~
{: .output}

## Variables only change value when something is assigned to them.

*   If we make one cell in a spreadsheet depend on another,
    and update the latter,
    the former updates automatically.
*   This does **not** happen in programming languages.

~~~
variable_one = 1
variable_two = 5 * variable_one
variable_one = 2
print('first is', variable_one, 'and second is', variable_two)
~~~
{: .language-python}
~~~
first is 2 and second is 5
~~~
{: .output}

*   The computer reads the value of `first` when doing the multiplication,
    creates a new value, and assigns it to `second`.
*   After that, `second` does not remember where it came from.

> ## Fractions
>
> What type of value is 3.4?
> How can you find out?
>
> > ## Solution
> >
> > It is a floating-point number (often abbreviated "float").
> > It is possible to find out by using the built-in function `type()`.
> >
> > ~~~
> > print(type(3.4))
> > ~~~
> > {: .language-python}
> > ~~~
> > <class 'float'>
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

> ## Automatic Type Conversion
>
> What type of value is 3.25 + 4?
>
> > ## Solution
> >
> > It is a float:
> > integers are automatically converted to floats as necessary.
> >
> > ~~~
> > result = 3.25 + 4
> > print(result, 'is', type(result))
> > ~~~
> > {: .language-python}
> > ~~~
> > 7.25 is <class 'float'>
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

> ## Choose a Type
>
> What type of value (integer, floating point number, or character string)
> would you use to represent each of the following?  Try to come up with more than one good answer for each problem.  For example, in  # 1, when would counting days with a floating point variable make more sense than using an integer?  
>
> 1. Number of days since the start of the year.
> 2. Time elapsed from the start of the year until now in days.
> 3. Serial number of a piece of lab equipment.
> 4. A lab specimen's age
> 5. Current population of a city.
> 6. Average population of a city over time.
>
> > ## Solution
> >
> > The answers to the questions are:
> > 1. Integer, since the number of days would lie between 1 and 365. 
> > 2. Floating point, since fractional days are required
> > 3. Character string if serial number contains letters and numbers, otherwise integer if the serial number consists only of numerals
> > 4. This will vary! How do you define a specimen's age? whole days since collection (integer)? date and time (string)?
> > 5. Choose floating point to represent population as large aggregates (eg millions), or integer to represent population in units of individuals.
> > 6. Floating point number, since an average is likely to have a fractional part.
> {: .solution}
{: .challenge}

> ## Division Types
>
> In Python 3, the `//` operator performs integer (whole-number) floor division, the `/` operator performs floating-point
> division, and the `%` (or *modulo*) operator calculates and returns the remainder from integer division:
>
> ~~~
> print('5 // 3:', 5 // 3)
> print('5 / 3:', 5 / 3)
> print('5 % 3:', 5 % 3)
> ~~~
> {: .language-python}
>
> ~~~
> 5 // 3: 1
> 5 / 3: 1.6666666666666667
> 5 % 3: 2
> ~~~
> {: .output}
>
> If `num_subjects` is the number of subjects taking part in a study,
> and `num_per_survey` is the number that can take part in a single survey,
> write an expression that calculates the number of surveys needed
> to reach everyone once.
>
> > ## Solution
> > We want the minimum number of surveys that reaches everyone once, which is
> > the rounded up value of `num_subjects/ num_per_survey`. This is 
> > equivalent to performing a floor division with `//` and adding 1. Before
> > the division we need to subtract 1 from the number of subjects to deal with 
> > the case where `num_subjects` is evenly divisible by `num_per_survey`.
> > ~~~
> > num_subjects = 600
> > num_per_survey = 42
> > num_surveys = (num_subjects - 1) // num_per_survey + 1
> >
> > print(num_subjects, 'subjects,', num_per_survey, 'per survey:', num_surveys)
> > ~~~
> > {: .language-python}
> > ~~~
> > 600 subjects, 42 per survey: 15
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

> ## Strings to Numbers
>
> Where reasonable, `float()` will convert a string to a floating point number,
> and `int()` will convert a floating point number to an integer:
>
> ~~~
> print("string to float:", float("3.4"))
> print("float to int:", int(3.4))
> ~~~
> {: .language-python}
>
> ~~~
> string to float: 3.4
> float to int: 3
> ~~~
> {: .output}
>
> If the conversion doesn't make sense, however, an error message will occur.
>
> ~~~
> print("string to float:", float("Hello world!"))
> ~~~
> {: .language-python}
>
> ~~~
> ---------------------------------------------------------------------------
> ValueError                                Traceback (most recent call last)
> <ipython-input-5-df3b790bf0a2> in <module>
> ----> 1 print("string to float:", float("Hello world!"))
>
> ValueError: could not convert string to float: 'Hello world!'
> ~~~
> {: .error}
>
> Given this information, what do you expect the following program to do?
>
> What does it actually do?
>
> Why do you think it does that?
>
> ~~~
> print("fractional string to int:", int("3.4"))
> ~~~
> {: .language-python}
> 
> > ## Solution
> > What do you expect this program to do? It would not be so unreasonable to expect the Python 3 `int` command to
> > convert the string "3.4" to 3.4 and an additional type conversion to 3. After all, Python 3 performs a lot of other
> > magic - isn't that part of its charm?
> >
> > ~~~
> > int("3.4")
> > ~~~
> > {: .language-python}
> > ~~~
> > ---------------------------------------------------------------------------
> > ValueError                                Traceback (most recent call last)
> > <ipython-input-2-ec6729dfccdc> in <module>
> > ----> 1 int("3.4")
> > ValueError: invalid literal for int() with base 10: '3.4'
> > ~~~
> > {: .output}
> > However, Python 3 throws an error. Why? To be consistent, possibly. If you ask Python to perform two consecutive
> > typecasts, you must convert it explicitly in code.
> > ~~~
> > int(float("3.4"))
> > ~~~
> > {: .language-python}
> > ~~~
> > 3
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

> ## Arithmetic with Different Types
>
> Which of the following will return the floating point number `2.0`?
> Note: there may be more than one right answer.
>
> ~~~
> first = 1.0
> second = "1"
> third = "1.1"
> ~~~
> {: .language-python}
>
> 1. `first + float(second)`
> 2. `float(second) + float(third)`
> 3. `first + int(third)`
> 4. `first + int(float(third))`
> 5. `int(first) + int(float(third))`
> 6. `2.0 * second`
>
> > ## Solution
> >
> > Answer: 1 and 4
> {: .solution}
{: .challenge}

> ## Complex Numbers
>
> Python provides complex numbers,
> which are written as `1.0+2.0j`.
> If `val` is a complex number,
> its real and imaginary parts can be accessed using *dot notation*
> as `val.real` and `val.imag`.
>
> ~~~
> a_complex_number = 6 + 2j
> print(a_complex_number.real)
> print(a_complex_number.imag)
> ~~~
> {: .language-python}
>
> ~~~
> 6.0
> 2.0
> ~~~
> {: .output}
>
>
> 1.  Why do you think Python uses `j` instead of `i` for the imaginary part?
> 2.  What do you expect `1 + 2j + 3` to produce?
> 3.  What do you expect `4j` to be?  What about `4 j` or `4 + j`?
> 
> > ## Solution
> >
> > 1. Standard mathematics treatments typically use `i` to denote an imaginary number. However, from media reports it
> > was an early convention established from electrical engineering that now presents a technically expensive area to
> > change. [Stack Overflow provides additional explanation and
> > discussion.](http://stackoverflow.com/questions/24812444/why-are-complex-numbers-in-python-denoted-with-j-instead-of-i)
> > 2. `(4+2j)`
> > 3. `4j` and `Syntax Error: invalid syntax`. In the latter cases, `j` is considered a variable and the statement
> > depends on if `j` is defined and if so, its assigned value.
> {: .solution}
{: .challenge}

---
title: "Built-in Functions and Help"
teaching: 15
exercises: 10
questions:
- "How can I use built-in functions?"
- "How can I find out what they do?"
- "What kind of errors can occur in programs?"
objectives:
- "Explain the purpose of functions."
- "Correctly call built-in Python functions."
- "Correctly nest calls to built-in functions."
- "Use help to display documentation for built-in functions."
- "Correctly describe situations in which SyntaxError and NameError occur."
keypoints:
- "Use comments to add documentation to programs."
- "A function may take zero or more arguments."
- "Commonly-used built-in functions include `max`, `min`, and `round`."
- "Functions may only work for certain (combinations of) arguments."
- "Functions may have default values for some arguments."
- "Use the built-in function `help` to get help for a function."
- "The Jupyter Notebook has two ways to get help."
- "Every function returns something."
- "Python reports a syntax error when it can't understand the source of a program."
- "Python reports a runtime error when something goes wrong while a program is executing."
- "Fix syntax errors by reading the source code, and runtime errors by tracing the program's execution."
---
## Use comments to add documentation to programs.

~~~
# This sentence isn't executed by Python.
adjustment = 0.5   # Neither is this - anything after '#' is ignored.
~~~
{: .language-python}

## A function may take zero or more arguments.

*   We have seen some functions already --- now let's take a closer look.
*   An *argument* is a value passed into a function.
*   `len` takes exactly one.
*   `int`, `str`, and `float` create a new value from an existing one.
*   `print` takes zero or more.
*   `print` with no arguments prints a blank line.
    *   Must always use parentheses, even if they're empty,
        so that Python knows a function is being called.

~~~
print('before')
print()
print('after')
~~~
{: .language-python}
~~~
before

after
~~~
{: .output}

## Every function returns something.

*   Every function call produces some result.
*   If the function doesn't have a useful result to return,
    it usually returns the special value `None`. `None` is a Python
    object that stands in anytime there is no value.

~~~
result = print('example')
print('result of print is', result)
~~~
{: .language-python}
~~~
example
result of print is None
~~~
{: .output}

## Commonly-used built-in functions include `max`, `min`, and `round`.

*   Use `max` to find the largest value of one or more values.
*   Use `min` to find the smallest.
*   Both work on character strings as well as numbers.
    *   "Larger" and "smaller" use (0-9, A-Z, a-z) to compare letters.

~~~
print(max(1, 2, 3))
print(min('a', 'A', '0'))
~~~
{: .language-python}
~~~
3
0
~~~
{: .output}

## Functions may only work for certain (combinations of) arguments.

*   `max` and `min` must be given at least one argument.
    *   "Largest of the empty set" is a meaningless question.
*   And they must be given things that can meaningfully be compared.

~~~
print(max(1, 'a'))
~~~
{: .language-python}
~~~
TypeError                                 Traceback (most recent call last)
<ipython-input-52-3f049acf3762> in <module>
----> 1 print(max(1, 'a'))

TypeError: '>' not supported between instances of 'str' and 'int'
~~~
{: .error}

## Functions may have default values for some arguments.

*   `round` will round off a floating-point number.
*   By default, rounds to zero decimal places.

~~~
round(3.712)
~~~
{: .language-python}
~~~
4
~~~
{: .output}

*   We can specify the number of decimal places we want.

~~~
round(3.712, 1)
~~~
{: .language-python}
~~~
3.7
~~~
{: .output}

## Functions attached to objects are called methods

* Functions take another form that will be common in the pandas episodes.
* Methods have parentheses like functions, but come after the variable.
* Some methods are used for internal Python operations, and are marked with double underlines.

~~~
my_string = 'Hello world!'  # creation of a string object 

print(len(my_string))       # the len function takes a string as an argument and returns the length of the string

print(my_string.swapcase()) # calling the swapcase method on the my_string object

print(my_string.__len__())  # calling the internal __len__ method on the my_string object, used by len(my_string)

~~~
{: .language-python}

~~~
12
hELLO WORLD!
12
~~~
{: .output}

* You might even see them chained together.  They operate left to right.

~~~
print(my_string.isupper())          # Not all the letters are uppercase
print(my_string.upper())            # This capitalizes all the letters

print(my_string.upper().isupper())  # Now all the letters are uppercase
~~~
{: .language-python}

~~~
False
HELLO WORLD
True
~~~
{: .output}

## Use the built-in function `help` to get help for a function.

*   Every built-in function has online documentation.

~~~
help(round)
~~~
{: .language-python}
~~~
Help on built-in function round in module builtins:

round(number, ndigits=None)
    Round a number to a given precision in decimal digits.
    
    The return value is an integer if ndigits is omitted or None.  Otherwise
    the return value has the same type as the number.  ndigits may be negative.
~~~
{: .output}

## The Jupyter Notebook has two ways to get help.

*   Option 1: Place the cursor near where the function is invoked in a cell
    (i.e., the function name or its parameters),
    * Hold down <kbd>Shift</kbd>, and press <kbd>Tab</kbd>.
    * Do this several times to expand the information returned.
*   Option 2: Type the function name in a cell with a question mark after it. Then run the cell.


## Python reports a syntax error when it can't understand the source of a program.

*   Won't even try to run the program if it can't be parsed.

~~~
# Forgot to close the quote marks around the string.
name = 'Feng
~~~
{: .language-python}
~~~
  File "<ipython-input-56-f42768451d55>", line 2
    name = 'Feng
                ^
SyntaxError: EOL while scanning string literal
~~~
{: .error}

~~~
# An extra '=' in the assignment.
age = = 52
~~~
{: .language-python}
~~~
  File "<ipython-input-57-ccc3df3cf902>", line 2
    age = = 52
          ^
SyntaxError: invalid syntax
~~~
{: .error}

*   Look more closely at the error message:

~~~
print("hello world"
~~~
{: .language-python}
~~~
  File "<ipython-input-6-d1cc229bf815>", line 1
    print ("hello world"
                        ^
SyntaxError: unexpected EOF while parsing
~~~
{: .error}

*   The message indicates a problem on first line of the input ("line 1").
    *   In this case the "ipython-input" section of the file name tells us that
        we are working with input into IPython,
        the Python interpreter used by the Jupyter Notebook.
*   The `-6-` part of the filename indicates that
    the error occurred in cell 6 of our Notebook.
*   Next is the problematic line of code,
    indicating the problem with a `^` pointer.

## <a name='runtime-error'></a> Python reports a runtime error when something goes wrong while a program is executing.

~~~
age = 53
remaining = 100 - aege # mis-spelled 'age'
~~~
{: .language-python}
~~~
NameError                                 Traceback (most recent call last)
<ipython-input-59-1214fb6c55fc> in <module>
      1 age = 53
----> 2 remaining = 100 - aege # mis-spelled 'age'

NameError: name 'aege' is not defined
~~~
{: .error}

*   Fix syntax errors by reading the source and runtime errors by tracing execution.

> ## What Happens When
>
> 1. Explain in simple terms the order of operations in the following program:
>    when does the addition happen, when does the subtraction happen,
>    when is each function called, etc.
> 2. What is the final value of `radiance`?
>
> ~~~
> radiance = 1.0
> radiance = max(2.1, 2.0 + min(radiance, 1.1 * radiance - 0.5))
> ~~~
> {: .language-python}
> > ## Solution
> > 1. Order of operations:
> >    1. `1.1 * radiance = 1.1`
> >    2. `1.1 - 0.5 = 0.6`
> >    3. `min(radiance, 0.6) = 0.6`
> >    4. `2.0 + 0.6 = 2.6`
> >    5. `max(2.1, 2.6) = 2.6`
> > 2. At the end, `radiance = 2.6`
> {: .solution}
{: .challenge}

> ## Spot the Difference
>
> 1. Predict what each of the `print` statements in the program below will print.
> 2. Does `max(len(rich), poor)` run or produce an error message?
>    If it runs, does its result make any sense?
>
> ~~~
> easy_string = "abc"
> print(max(easy_string))
> rich = "gold"
> poor = "tin"
> print(max(rich, poor))
> print(max(len(rich), len(poor)))
> ~~~
> {: .language-python}
> > ## Solution
> > ~~~
> > print(max(easy_string))
> > ~~~
> > {: .language-python}
> > ~~~
> > c
> > ~~~
> > {: .output}
> > ~~~
> > print(max(rich, poor))
> > ~~~
> > {: .language-python}
> > ~~~
> > tin
> > ~~~
> > {: .output}
> > ~~~
> > print(max(len(rich), len(poor)))
> > ~~~
> > {: .language-python}
> > ~~~
> > 4
> > ~~~
> > {: .output}
> > `max(len(rich), poor)` throws a TypeError. This turns into `max(4, 'tin')` and 
> > as we discussed earlier a string and integer cannot meaningfully be compared.
> > ~~~
> > TypeError                                 Traceback (most recent call last)
> > <ipython-input-65-bc82ad05177a> in <module>
> > ----> 1 max(len(rich), poor)
> > 
> > TypeError: '>' not supported between instances of 'str' and 'int'
> > ~~~
> > {: .error }
> {: .solution}
{: .challenge}

> ## Why Not?
>
> Why is it that `max` and `min` do not return `None` when they are called with no arguments?
>
> > ## Solution
> > `max` and `min` return TypeErrors in this case because the correct number of parameters
> > was not supplied. If it just returned `None`, the error would be much harder to trace as it
> > would likely be stored into a variable and used later in the program, only to likely throw
> > a runtime error.
> {: .solution}
{: .challenge}

> ## Last Character of a String
>
> If Python starts counting from zero,
> and `len` returns the number of characters in a string,
> what index expression will get the last character in the string `name`?
> (Note: we will see a simpler way to do this in a later episode.)
>
> > ## Solution
> >
> > `name[len(name) - 1]`
> {: .solution}
{: .challenge}

> ## Explore the Python docs!
>
> The [official Python documentation](https://docs.python.org/3/) is arguably the most complete
> source of information about the language. It is available in different languages and contains a lot of useful
> resources. The [Built-in Functions page](https://docs.python.org/3/library/functions.html) contains a catalogue of
> all of these functions, including the ones that we've covered in this lesson. Some of these are more advanced and 
> unnecessary at the moment, but others are very simple and useful.
> 
{: .callout}
    
---
title: "Libraries"
teaching: 10
exercises: 10
questions:
- "How can I use software that other people have written?"
- "How can I find out what that software does?"
objectives:
- "Explain what software libraries are and why programmers create and use them."
- "Write programs that import and use modules from Python's standard library."
- "Find and read documentation for the standard library interactively (in the interpreter) and online."
keypoints:
- "Most of the power of a programming language is in its libraries."
- "A program must import a library module in order to use it."
- "Use `help` to learn about the contents of a library module."
- "Import specific items from a library to shorten programs."
- "Create an alias for a library when importing it to shorten programs."
---
## Most of the power of a programming language is in its libraries.

*   A *library* is a collection of files (called *modules*) that contains
    functions for use by other programs.
    *   May also contain data values (e.g., numerical constants) and other things.
    *   Library's contents are supposed to be related, but there's no way to enforce that.
*   The Python [standard library][stdlib] is an extensive suite of modules that comes
    with Python itself.
*   Many additional libraries are available from [PyPI][pypi] (the Python Package Index).
*   We will see later how to write new libraries.

> ## Libraries and modules
>
> A library is a collection of modules, but the terms are often used
> interchangeably, especially since many libraries only consist of a single
> module, so don't worry if you mix them.
{: .callout}


## A program must import a library module before using it.

*   Use `import` to load a library module into a program's memory.
*   Then refer to things from the module as `module_name.thing_name`.
    *   Python uses `.` to mean "part of".
*   Using `math`, one of the modules in the standard library:

~~~
import math

print('pi is', math.pi)
print('cos(pi) is', math.cos(math.pi))
~~~
{: .language-python}
~~~
pi is 3.141592653589793
cos(pi) is -1.0
~~~
{: .output}

*   Have to refer to each item with the module's name.
    *   `math.cos(pi)` won't work: the reference to `pi`
        doesn't somehow "inherit" the function's reference to `math`.

## Use `help` to learn about the contents of a library module.

*   Works just like help for a function.

~~~
help(math)
~~~
{: .language-python}
~~~
Help on module math:

NAME
    math

MODULE REFERENCE
    http://docs.python.org/3/library/math

    The following documentation is automatically generated from the Python
    source files.  It may be incomplete, incorrect or include features that
    are considered implementation detail and may vary between Python
    implementations.  When in doubt, consult the module reference at the
    location listed above.

DESCRIPTION
    This module is always available.  It provides access to the
    mathematical functions defined by the C standard.

FUNCTIONS
    acos(x, /)
        Return the arc cosine (measured in radians) of x.
⋮ ⋮ ⋮
~~~
{: .output}

## Import specific items from a library module to shorten programs.

*   Use `from ... import ...` to load only specific items from a library module.
*   Then refer to them directly without library name as prefix.

~~~
from math import cos, pi

print('cos(pi) is', cos(pi))
~~~
{: .language-python}
~~~
cos(pi) is -1.0
~~~
{: .output}

## Create an alias for a library module when importing it to shorten programs.

*   Use `import ... as ...` to give a library a short *alias* while importing it.
*   Then refer to items in the library using that shortened name.

~~~
import math as m

print('cos(pi) is', m.cos(m.pi))
~~~
{: .language-python}
~~~
cos(pi) is -1.0
~~~
{: .output}

*   Commonly used for libraries that are frequently used or have long names.
    *   E.g., the `matplotlib` plotting library is often aliased as `mpl`.
*   But can make programs harder to understand,
    since readers must learn your program's aliases.

> ## Exploring the Math Module
>
> 1. What function from the `math` module can you use to calculate a square root
>    *without* using `sqrt`?
> 2. Since the library contains this function, why does `sqrt` exist?
>
> > ## Solution
> > 1. Using `help(math)` we see that we've got `pow(x,y)` in addition to `sqrt(x)`,
> >    so we could use `pow(x, 0.5)` to find a square root.
> > 2. The `sqrt(x)` function is arguably more readable than `pow(x, 0.5)` when
> >    implementing equations. Readability is a cornerstone of good programming, so it
> >    makes sense to provide a special function for this specific common case.
> >
> >    Also, the design of Python's `math` library has its origin in the C standard,
> >    which includes both `sqrt(x)` and `pow(x,y)`, so a little bit of the history
> >    of programming is showing in Python's function names.
> {: .solution}
{: .challenge}

> ## Locating the Right Module
>
> You want to select a random character from a string:
>
> ~~~
> bases = 'ACTTGCTTGAC'
> ~~~
> {: .language-python}
>
> 1. Which [standard library][stdlib] module could help you?
> 2. Which function would you select from that module? Are there alternatives?
> 3. Try to write a program that uses the function.
>
> > ## Solution
> >
> > The [random module][randommod] seems like it could help.
> >
> > The string has 11 characters, each having a positional index from 0 to 10.
> > You could use the [`random.randrange`](https://docs.python.org/3/library/random.html#random.randrange)
> > or [`random.randint`](https://docs.python.org/3/library/random.html#random.randint) functions
> > to get a random integer between 0 and 10, and then select the `bases` character at that index:
> >
> > ~~~
> > from random import randrange
> >
> > random_index = randrange(len(bases))
> > print(bases[random_index])
> > ~~~
> > {: .language-python}
> >
> > or more compactly:
> >
> > ~~~
> > from random import randrange
> >
> > print(bases[randrange(len(bases))])
> > ~~~
> > {: .language-python}
> >
> > Perhaps you found the [`random.sample`](https://docs.python.org/3/library/random.html#random.sample) function? 
> > It allows for slightly less typing but might be a bit harder to understand just by reading:
> >
> > ~~~
> > from random import sample
> >
> > print(sample(bases, 1)[0])
> > ~~~
> > {: .language-python}
> >
> > Note that this function returns a list of values. We will learn about
> > lists in [episode 11]({{ page.root }}/11-lists/).
> > 
> > The simplest and shortest solution is the [`random.choice`](https://docs.python.org/3/library/random.html#random.choice) 
> > function that does exactly what we want:
> > 
> > ~~~
> > from random import choice
> >
> > print(choice(bases))
> > ~~~
> > {: .language-python}
> >
> {: .solution}
{: .challenge}


> ## Jigsaw Puzzle (Parson's Problem) Programming Example
>
> Rearrange the following statements so that a random
> DNA base is printed and its index in the string. 
> Not all statements may be needed.  Feel free to use/add
> intermediate variables.
>
> ~~~
> bases="ACTTGCTTGAC"
> import math
> import random
> ___ = random.randrange(n_bases)
> ___ = len(bases)
> print("random base ", bases[___], "base index", ___)
> ~~~
> {: .language-python}
>
> > ## Solution
> >
> > ~~~
> > import math 
> > import random
> > bases = "ACTTGCTTGAC" 
> > n_bases = len(bases)
> > idx = random.randrange(n_bases)
> > print("random base", bases[idx], "base index", idx)
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## When Is Help Available?
>
> When a colleague of yours types `help(math)`,
> Python reports an error:
>
> ~~~
> NameError: name 'math' is not defined
> ~~~
> {: .error}
>
> What has your colleague forgotten to do?
>
> > ## Solution
> >
> > Importing the math module (`import math`)
> {: .solution}
{: .challenge}

> ## Importing With Aliases
>
> 1. Fill in the blanks so that the program below prints `90.0`.
> 2. Rewrite the program so that it uses `import` *without* `as`.
> 3. Which form do you find easier to read?
>
> ~~~
> import math as m
> angle = ____.degrees(____.pi / 2)
> print(____)
> ~~~
> {: .language-python}
>
> > ## Solution
> >
> > ~~~
> > import math as m
> > angle = m.degrees(m.pi / 2)
> > print(angle)
> > ~~~
> > {: .language-python}
> >
> > can be written as
> >
> > ~~~
> > import math
> > angle = math.degrees(math.pi / 2)
> > print(angle)
> > ~~~
> > {: .language-python}
> >
> > Since you just wrote the code and are familiar with it, you might actually
> > find the first version easier to read. But when trying to read a huge piece
> > of code written by someone else, or when getting back to your own huge piece
> > of code after several months, non-abbreviated names are often easier, except
> > where there are clear abbreviation conventions.
> {: .solution}
{: .challenge}

> ## There Are Many Ways To Import Libraries!
>
> Match the following print statements with the appropriate library calls.
>
> Print commands:
>
> 1. `print("sin(pi/2) =", sin(pi/2))`
> 2. `print("sin(pi/2) =", m.sin(m.pi/2))`
> 3. `print("sin(pi/2) =", math.sin(math.pi/2))`
>
> Library calls:
>
> 1. `from math import sin, pi`
> 2. `import math`
> 3. `import math as m`
> 4. `from math import *`
>
> > ## Solution
> >
> > 1. Library calls 1 and 4. In order to directly refer to `sin` and `pi` without
> >    the library name as prefix, you need to use the `from ... import ...`
> >    statement. Whereas library call 1 specifically imports the two functions
> >    `sin` and `pi`, library call 4 imports all functions in the `math` module.
> > 2. Library call 3. Here `sin` and `pi` are referred to with a shortened library
> >    name `m` instead of `math`. Library call 3 does exactly that using the
> >    `import ... as ...` syntax - it creates an alias for `math` in the form of
> >    the shortened name `m`.
> > 3. Library call 2. Here `sin` and `pi` are referred to with the regular library
> >    name `math`, so the regular `import ...` call suffices.
> >
> > __Note:__ although library call 4 works, importing all names from a module using a wildcard 
> > import is [not recommended][pep8-imports] as it makes it unclear which names from the module
> > are used in the code. In general it is best to make your imports as specific as possible and to 
> > only import what your code uses. In library call 1, the `import` statement explicitly tells us
> > that the `sin` function is imported from the `math` module, but library call 4 does not
> > convey this information.
> {: .solution}
{: .challenge}

> ## Importing Specific Items
>
> 1. Fill in the blanks so that the program below prints `90.0`.
> 2. Do you find this version easier to read than preceding ones?
> 3. Why *wouldn't* programmers always use this form of `import`?
>
> ~~~
> ____ math import ____, ____
> angle = degrees(pi / 2)
> print(angle)
> ~~~
> {: .language-python}
>
> > ## Solution
> >
> > ~~~
> > from math import degrees, pi
> > angle = degrees(pi / 2)
> > print(angle)
> > ~~~
> > {: .language-python}
> >
> > Most likely you find this version easier to read since it's less dense.
> > The main reason not to use this form of import is to avoid name clashes.
> > For instance, you wouldn't import `degrees` this way if you also wanted to
> > use the name `degrees` for a variable or function of your own. Or if you
> > were to also import a function named `degrees` from another library.
> {: .solution}
{: .challenge}

> ## Reading Error Messages
>
> 1. Read the code below and try to identify what the errors are without running it.
> 2. Run the code, and read the error message. What type of error is it?
>
> ~~~
> from math import log
> log(0)
> ~~~
> {: .language-python}
>
> > ## Solution
> > ~~~
> > ---------------------------------------------------------------------------
> > ValueError                                Traceback (most recent call last)
> > <ipython-input-1-d72e1d780bab> in <module>
> >       1 from math import log
> > ----> 2 log(0)
> > 
> > ValueError: math domain error
> > ~~~
> > {: .output}
> >
> > 1. The logarithm of `x` is only defined for `x > 0`, so 0 is outside the
> >    domain of the function.
> > 2. You get an error of type `ValueError`, indicating that the function
> >    received an inappropriate argument value. The additional message
> >    "math domain error" makes it clearer what the problem is.
> {: .solution}
{: .challenge}

[pypi]: https://pypi.python.org/pypi/
[stdlib]: https://docs.python.org/3/library/
[randommod]: https://docs.python.org/3/library/random.html
[pep8-imports]: https://pep8.org/#imports

    
---
title: "Reading Tabular Data into DataFrames"
teaching: 10
exercises: 10
questions:
- "How can I read tabular data?"
objectives:
- "Import the Pandas library."
- "Use Pandas to load a simple CSV data set."
- "Get some basic information about a Pandas DataFrame."
keypoints:
- "Use the Pandas library to get basic statistics out of tabular data."
- "Use `index_col` to specify that a column's values should be used as row headings."
- "Use `DataFrame.info` to find out more about a dataframe."
- "The `DataFrame.columns` variable stores information about the dataframe's columns."
- "Use `DataFrame.T` to transpose a dataframe."
- "Use `DataFrame.describe` to get summary statistics about data."
---
## Use the Pandas library to do statistics on tabular data.

*   Pandas is a widely-used Python library for statistics, particularly on tabular data.
*   Borrows many features from R's dataframes.
    *   A 2-dimensional table whose columns have names
        and potentially have different data types.
*   Load it with `import pandas as pd`. The alias pd is commonly used for Pandas.
*   Read a Comma Separated Values (CSV) data file with `pd.read_csv`.
    *   Argument is the name of the file to be read.
    *   Assign result to a variable to store the data that was read.

~~~
import pandas as pd

data = pd.read_csv('data/gapminder_gdp_oceania.csv')
print(data)
~~~
{: .language-python}
~~~
       country  gdpPercap_1952  gdpPercap_1957  gdpPercap_1962  \
0    Australia     10039.59564     10949.64959     12217.22686
1  New Zealand     10556.57566     12247.39532     13175.67800

   gdpPercap_1967  gdpPercap_1972  gdpPercap_1977  gdpPercap_1982  \
0     14526.12465     16788.62948     18334.19751     19477.00928
1     14463.91893     16046.03728     16233.71770     17632.41040

   gdpPercap_1987  gdpPercap_1992  gdpPercap_1997  gdpPercap_2002  \
0     21888.88903     23424.76683     26997.93657     30687.75473
1     19007.19129     18363.32494     21050.41377     23189.80135

   gdpPercap_2007
0     34435.36744
1     25185.00911
~~~
{: .output}

*   The columns in a dataframe are the observed variables, and the rows are the observations.
*   Pandas uses backslash `\` to show wrapped lines when output is too wide to fit the screen.

> ## File Not Found
>
> Our lessons store their data files in a `data` sub-directory,
> which is why the path to the file is `data/gapminder_gdp_oceania.csv`.
> If you forget to include `data/`,
> or if you include it but your copy of the file is somewhere else,
> you will get a [runtime error]({{ page.root }}/04-built-in/#runtime-error)
> that ends with a line like this:
>
> ~~~
> FileNotFoundError: [Errno 2] No such file or directory: 'data/gapminder_gdp_oceania.csv'
> ~~~
> {: .error}
{: .callout}

## Use `index_col` to specify that a column's values should be used as row headings.

*   Row headings are numbers (0 and 1 in this case).
*   Really want to index by country.
*   Pass the name of the column to `read_csv` as its `index_col` parameter to do this.

~~~
data = pd.read_csv('data/gapminder_gdp_oceania.csv', index_col='country')
print(data)
~~~
{: .language-python}
~~~
             gdpPercap_1952  gdpPercap_1957  gdpPercap_1962  gdpPercap_1967  \
country
Australia       10039.59564     10949.64959     12217.22686     14526.12465
New Zealand     10556.57566     12247.39532     13175.67800     14463.91893

             gdpPercap_1972  gdpPercap_1977  gdpPercap_1982  gdpPercap_1987  \
country
Australia       16788.62948     18334.19751     19477.00928     21888.88903
New Zealand     16046.03728     16233.71770     17632.41040     19007.19129

             gdpPercap_1992  gdpPercap_1997  gdpPercap_2002  gdpPercap_2007
country
Australia       23424.76683     26997.93657     30687.75473     34435.36744
New Zealand     18363.32494     21050.41377     23189.80135     25185.00911
~~~
{: .output}

## Use the `DataFrame.info()` method to find out more about a dataframe.

~~~
data.info()
~~~
{: .language-python}
~~~
<class 'pandas.core.frame.DataFrame'>
Index: 2 entries, Australia to New Zealand
Data columns (total 12 columns):
gdpPercap_1952    2 non-null float64
gdpPercap_1957    2 non-null float64
gdpPercap_1962    2 non-null float64
gdpPercap_1967    2 non-null float64
gdpPercap_1972    2 non-null float64
gdpPercap_1977    2 non-null float64
gdpPercap_1982    2 non-null float64
gdpPercap_1987    2 non-null float64
gdpPercap_1992    2 non-null float64
gdpPercap_1997    2 non-null float64
gdpPercap_2002    2 non-null float64
gdpPercap_2007    2 non-null float64
dtypes: float64(12)
memory usage: 208.0+ bytes
~~~
{: .output}

*   This is a `DataFrame`
*   Two rows named `'Australia'` and `'New Zealand'`
*   Twelve columns, each of which has two actual 64-bit floating point values.
    *   We will talk later about null values, which are used to represent missing observations.
*   Uses 208 bytes of memory.

## The `DataFrame.columns` variable stores information about the dataframe's columns.

*   Note that this is data, *not* a method.  (It doesn't have parentheses.)
    *   Like `math.pi`.
    *   So do not use `()` to try to call it.
*   Called a *member variable*, or just *member*.

~~~
print(data.columns)
~~~
{: .language-python}
~~~
Index(['gdpPercap_1952', 'gdpPercap_1957', 'gdpPercap_1962', 'gdpPercap_1967',
       'gdpPercap_1972', 'gdpPercap_1977', 'gdpPercap_1982', 'gdpPercap_1987',
       'gdpPercap_1992', 'gdpPercap_1997', 'gdpPercap_2002', 'gdpPercap_2007'],
      dtype='object')
~~~
{: .output}

## Use `DataFrame.T` to transpose a dataframe.

*   Sometimes want to treat columns as rows and vice versa.
*   Transpose (written `.T`) doesn't copy the data, just changes the program's view of it.
*   Like `columns`, it is a member variable.

~~~
print(data.T)
~~~
{: .language-python}
~~~
country           Australia  New Zealand
gdpPercap_1952  10039.59564  10556.57566
gdpPercap_1957  10949.64959  12247.39532
gdpPercap_1962  12217.22686  13175.67800
gdpPercap_1967  14526.12465  14463.91893
gdpPercap_1972  16788.62948  16046.03728
gdpPercap_1977  18334.19751  16233.71770
gdpPercap_1982  19477.00928  17632.41040
gdpPercap_1987  21888.88903  19007.19129
gdpPercap_1992  23424.76683  18363.32494
gdpPercap_1997  26997.93657  21050.41377
gdpPercap_2002  30687.75473  23189.80135
gdpPercap_2007  34435.36744  25185.00911
~~~
{: .output}

## Use `DataFrame.describe()` to get summary statistics about data.

`DataFrame.describe()` gets the summary statistics of only the columns that have numerical data. 
All other columns are ignored, unless you use the argument `include='all'`.
~~~
print(data.describe())
~~~
{: .language-python}
~~~
       gdpPercap_1952  gdpPercap_1957  gdpPercap_1962  gdpPercap_1967  \
count        2.000000        2.000000        2.000000        2.000000
mean     10298.085650    11598.522455    12696.452430    14495.021790
std        365.560078      917.644806      677.727301       43.986086
min      10039.595640    10949.649590    12217.226860    14463.918930
25%      10168.840645    11274.086022    12456.839645    14479.470360
50%      10298.085650    11598.522455    12696.452430    14495.021790
75%      10427.330655    11922.958888    12936.065215    14510.573220
max      10556.575660    12247.395320    13175.678000    14526.124650

       gdpPercap_1972  gdpPercap_1977  gdpPercap_1982  gdpPercap_1987  \
count         2.00000        2.000000        2.000000        2.000000
mean      16417.33338    17283.957605    18554.709840    20448.040160
std         525.09198     1485.263517     1304.328377     2037.668013
min       16046.03728    16233.717700    17632.410400    19007.191290
25%       16231.68533    16758.837652    18093.560120    19727.615725
50%       16417.33338    17283.957605    18554.709840    20448.040160
75%       16602.98143    17809.077557    19015.859560    21168.464595
max       16788.62948    18334.197510    19477.009280    21888.889030

       gdpPercap_1992  gdpPercap_1997  gdpPercap_2002  gdpPercap_2007
count        2.000000        2.000000        2.000000        2.000000
mean     20894.045885    24024.175170    26938.778040    29810.188275
std       3578.979883     4205.533703     5301.853680     6540.991104
min      18363.324940    21050.413770    23189.801350    25185.009110
25%      19628.685413    22537.294470    25064.289695    27497.598692
50%      20894.045885    24024.175170    26938.778040    29810.188275
75%      22159.406358    25511.055870    28813.266385    32122.777857
max      23424.766830    26997.936570    30687.754730    34435.367440
~~~
{: .output}

*   Not particularly useful with just two records,
    but very helpful when there are thousands.

> ## Reading Other Data
>
> Read the data in `gapminder_gdp_americas.csv`
> (which should be in the same directory as `gapminder_gdp_oceania.csv`)
> into a variable called `americas`
> and display its summary statistics.
>
> > ## Solution
> > To read in a CSV, we use `pd.read_csv` and pass the filename `'data/gapminder_gdp_americas.csv'` to it.
> > We also once again pass the column name `'country'` to the parameter `index_col` in order to index by country.
> > The summary statistics can be displayed with the `DataFrame.describe()` method.
> > ~~~
> > americas = pd.read_csv('data/gapminder_gdp_americas.csv', index_col='country')
> > americas.describe()
> > ~~~
> >{: .language-python}
> {: .solution}
{: .challenge}

> ## Inspecting Data
>
> After reading the data for the Americas,
> use `help(americas.head)` and `help(americas.tail)`
> to find out what `DataFrame.head` and `DataFrame.tail` do.
>
> 1.  What method call will display the first three rows of this data?
> 2.  What method call will display the last three columns of this data?
>     (Hint: you may need to change your view of the data.)
>
> > ## Solution
> > 1. We can check out the first five rows of `americas` by executing `americas.head()`
> >    (allowing us to view the head of the DataFrame). We can specify the number of rows we wish
> >    to see by specifying the parameter `n` in our call
> >    to `americas.head()`. To view the first three rows, execute:
> >
> >    ~~~
> >    americas.head(n=3)
> >    ~~~
> >    {: .language-python}
> >    ~~~
> >              continent  gdpPercap_1952  gdpPercap_1957  gdpPercap_1962  \
> >    country
> >    Argentina  Americas     5911.315053     6856.856212     7133.166023
> >    Bolivia    Americas     2677.326347     2127.686326     2180.972546
> >    Brazil     Americas     2108.944355     2487.365989     3336.585802
> >
> >               gdpPercap_1967  gdpPercap_1972  gdpPercap_1977  gdpPercap_1982  \
> >    country
> >    Argentina     8052.953021     9443.038526    10079.026740     8997.897412
> >    Bolivia       2586.886053     2980.331339     3548.097832     3156.510452
> >    Brazil        3429.864357     4985.711467     6660.118654     7030.835878
> >
> >               gdpPercap_1987  gdpPercap_1992  gdpPercap_1997  gdpPercap_2002  \
> >    country
> >    Argentina     9139.671389     9308.418710    10967.281950     8797.640716
> >    Bolivia       2753.691490     2961.699694     3326.143191     3413.262690
> >    Brazil        7807.095818     6950.283021     7957.980824     8131.212843
> >
> >               gdpPercap_2007
> >    country
> >    Argentina    12779.379640
> >    Bolivia       3822.137084
> >    Brazil        9065.800825
> >    ~~~
> >    {: .output}
> > 2. To check out the last three rows of `americas`, we would use the command,
> >    `americas.tail(n=3)`, analogous to `head()` used above. However, here we want to look at
> >    the last three columns so we need to change our view and then use `tail()`. To do so, we
> >     create a new DataFrame in which rows and columns are switched:
> >
> >    ~~~
> >    americas_flipped = americas.T
> >    ~~~
> >    {: .language-python}
> >
> >    We can then view the last three columns of `americas` by viewing the last three rows
> >    of `americas_flipped`:
> >    ~~~
> >    americas_flipped.tail(n=3)
> >    ~~~
> >    {: .language-python}
> >    ~~~
> >    country        Argentina  Bolivia   Brazil   Canada    Chile Colombia  \
> >    gdpPercap_1997   10967.3  3326.14  7957.98  28954.9  10118.1  6117.36
> >    gdpPercap_2002   8797.64  3413.26  8131.21    33329  10778.8  5755.26
> >    gdpPercap_2007   12779.4  3822.14   9065.8  36319.2  13171.6  7006.58
> >
> >    country        Costa Rica     Cuba Dominican Republic  Ecuador    ...     \
> >    gdpPercap_1997    6677.05  5431.99             3614.1  7429.46    ...
> >    gdpPercap_2002    7723.45  6340.65            4563.81  5773.04    ...
> >    gdpPercap_2007    9645.06   8948.1            6025.37  6873.26    ...
> >
> >    country          Mexico Nicaragua   Panama Paraguay     Peru Puerto Rico  \
> >    gdpPercap_1997   9767.3   2253.02  7113.69   4247.4  5838.35     16999.4
> >    gdpPercap_2002  10742.4   2474.55  7356.03  3783.67  5909.02     18855.6
> >    gdpPercap_2007  11977.6   2749.32  9809.19  4172.84  7408.91     19328.7
> >
> >    country        Trinidad and Tobago United States  Uruguay Venezuela
> >    gdpPercap_1997             8792.57       35767.4  9230.24   10165.5
> >    gdpPercap_2002             11460.6       39097.1     7727   8605.05
> >    gdpPercap_2007             18008.5       42951.7  10611.5   11415.8
> >    ~~~
> >    {: .output}
> >    
> >    This shows the data that we want, but we may prefer to display three columns instead of three rows,
> >    so we can flip it back:
> >    ~~~
> >    americas_flipped.tail(n=3).T    
> >    ~~~
> >    {: .language-python}    
> >    __Note:__ we could have done the above in a single line of code by 'chaining' the commands:
> >    ~~~
> >    americas.T.tail(n=3).T
> >    ~~~
> >    {: .language-python}
> {: .solution}
{: .challenge}


> ## Reading Files in Other Directories
>
> The data for your current project is stored in a file called `microbes.csv`,
> which is located in a folder called `field_data`.
> You are doing analysis in a notebook called `analysis.ipynb`
> in a sibling folder called `thesis`:
>
> ~~~
> your_home_directory
> +-- field_data/
> |   +-- microbes.csv
> +-- thesis/
>     +-- analysis.ipynb
> ~~~
> {: .output}
>
> What value(s) should you pass to `read_csv` to read `microbes.csv` in `analysis.ipynb`?
> 
> > ## Solution
> > We need to specify the path to the file of interest in the call to `pd.read_csv`. We first need to 'jump' out of
> > the folder `thesis` using '../' and then into the folder `field_data` using 'field_data/'. Then we can specify the filename `microbes.csv.
> > The result is as follows:
> > ~~~
> > data_microbes = pd.read_csv('../field_data/microbes.csv')
> > ~~~
> >{: .language-python}
> {: .solution}
{: .challenge}

> ## Writing Data
> 
> As well as the `read_csv` function for reading data from a file,
> Pandas provides a `to_csv` function to write dataframes to files.
> Applying what you've learned about reading from files,
> write one of your dataframes to a file called `processed.csv`.
> You can use `help` to get information on how to use `to_csv`.
> > ## Solution
> > In order to write the DataFrame `americas` to a file called `processed.csv`, execute the following command:
> > ~~~
> > americas.to_csv('processed.csv')
> > ~~~
> >{: .language-python}
> > For help on `to_csv`, you could execute, for example:
> > ~~~
> > help(americas.to_csv)
> > ~~~
> >{: .language-python}
> > Note that `help(to_csv)` throws an error! This is a subtlety and is due to the fact that `to_csv` is NOT a function in 
> > and of itself and the actual call is `americas.to_csv`. 
> {: .solution}
{: .challenge}


---
title: "Pandas DataFrames"
teaching: 15
exercises: 15
questions:
- "How can I do statistical analysis of tabular data?"
objectives:
- "Select individual values from a Pandas dataframe."
- "Select entire rows or entire columns from a dataframe."
- "Select a subset of both rows and columns from a dataframe in a single operation."
- "Select a subset of a dataframe by a single Boolean criterion."
keypoints:
- "Use `DataFrame.iloc[..., ...]` to select values by integer location."
- "Use `:` on its own to mean all columns or all rows."
- "Select multiple columns or rows using `DataFrame.loc` and a named slice."
- "Result of slicing can be used in further operations."
- "Use comparisons to select data based on value."
- "Select values or NaN using a Boolean mask."
---

## Note about Pandas DataFrames/Series

A [DataFrame][pandas-dataframe] is a collection of [Series][pandas-series];
The DataFrame is the way Pandas represents a table, and Series is the data-structure
Pandas use to represent a column.

Pandas is built on top of the [Numpy][numpy] library, which in practice means that
most of the methods defined for Numpy Arrays apply to Pandas Series/DataFrames.

What makes Pandas so attractive is the powerful interface to access individual records
of the table, proper handling of missing values, and relational-databases operations
between DataFrames.

## Selecting values

To access a value at the position `[i,j]` of a DataFrame, we have two options, depending on
what is the meaning of `i` in use.
Remember that a DataFrame provides an *index* as a way to identify the rows of the table;
a row, then, has a *position* inside the table as well as a *label*, which
uniquely identifies its *entry* in the DataFrame.

## Use `DataFrame.iloc[..., ...]` to select values by their (entry) position

*   Can specify location by numerical index analogously to 2D version of character selection in strings.

~~~
import pandas as pd
data = pd.read_csv('data/gapminder_gdp_europe.csv', index_col='country')
print(data.iloc[0, 0])
~~~
{: .language-python}
~~~
1601.056136
~~~
{: .output}

## Use `DataFrame.loc[..., ...]` to select values by their (entry) label.

*   Can specify location by row name analogously to 2D version of dictionary keys.

~~~
print(data.loc["Albania", "gdpPercap_1952"])
~~~
{: .language-python}
~~~
1601.056136
~~~
{: .output}
## Use `:` on its own to mean all columns or all rows.

*   Just like Python's usual slicing notation.

~~~
print(data.loc["Albania", :])
~~~
{: .language-python}
~~~
gdpPercap_1952    1601.056136
gdpPercap_1957    1942.284244
gdpPercap_1962    2312.888958
gdpPercap_1967    2760.196931
gdpPercap_1972    3313.422188
gdpPercap_1977    3533.003910
gdpPercap_1982    3630.880722
gdpPercap_1987    3738.932735
gdpPercap_1992    2497.437901
gdpPercap_1997    3193.054604
gdpPercap_2002    4604.211737
gdpPercap_2007    5937.029526
Name: Albania, dtype: float64
~~~
{: .output}

*   Would get the same result printing `data.loc["Albania"]` (without a second index).

~~~
print(data.loc[:, "gdpPercap_1952"])
~~~
{: .language-python}
~~~
country
Albania                    1601.056136
Austria                    6137.076492
Belgium                    8343.105127
⋮ ⋮ ⋮
Switzerland               14734.232750
Turkey                     1969.100980
United Kingdom             9979.508487
Name: gdpPercap_1952, dtype: float64
~~~
{: .output}

*   Would get the same result printing `data["gdpPercap_1952"]`
*   Also get the same result printing `data.gdpPercap_1952` (not recommended, because easily confused with `.` notation for methods)

## Select multiple columns or rows using `DataFrame.loc` and a named slice.

~~~
print(data.loc['Italy':'Poland', 'gdpPercap_1962':'gdpPercap_1972'])
~~~
{: .language-python}
~~~
             gdpPercap_1962  gdpPercap_1967  gdpPercap_1972
country
Italy           8243.582340    10022.401310    12269.273780
Montenegro      4649.593785     5907.850937     7778.414017
Netherlands    12790.849560    15363.251360    18794.745670
Norway         13450.401510    16361.876470    18965.055510
Poland          5338.752143     6557.152776     8006.506993
~~~
{: .output}

In the above code, we discover that **slicing using `loc` is inclusive at both
ends**, which differs from **slicing using `iloc`**, where slicing indicates
everything up to but not including the final index. 


## Result of slicing can be used in further operations.

*   Usually don't just print a slice.
*   All the statistical operators that work on entire dataframes
    work the same way on slices.
*   E.g., calculate max of a slice.

~~~
print(data.loc['Italy':'Poland', 'gdpPercap_1962':'gdpPercap_1972'].max())
~~~
{: .language-python}
~~~
gdpPercap_1962    13450.40151
gdpPercap_1967    16361.87647
gdpPercap_1972    18965.05551
dtype: float64
~~~
{: .output}

~~~
print(data.loc['Italy':'Poland', 'gdpPercap_1962':'gdpPercap_1972'].min())
~~~
{: .language-python}
~~~
gdpPercap_1962    4649.593785
gdpPercap_1967    5907.850937
gdpPercap_1972    7778.414017
dtype: float64
~~~
{: .output}

## Use comparisons to select data based on value.

*   Comparison is applied element by element.
*   Returns a similarly-shaped dataframe of `True` and `False`.

~~~
# Use a subset of data to keep output readable.
subset = data.loc['Italy':'Poland', 'gdpPercap_1962':'gdpPercap_1972']
print('Subset of data:\n', subset)

# Which values were greater than 10000 ?
print('\nWhere are values large?\n', subset > 10000)
~~~
{: .language-python}
~~~
Subset of data:
             gdpPercap_1962  gdpPercap_1967  gdpPercap_1972
country
Italy           8243.582340    10022.401310    12269.273780
Montenegro      4649.593785     5907.850937     7778.414017
Netherlands    12790.849560    15363.251360    18794.745670
Norway         13450.401510    16361.876470    18965.055510
Poland          5338.752143     6557.152776     8006.506993

Where are values large?
            gdpPercap_1962 gdpPercap_1967 gdpPercap_1972
country
Italy                False           True           True
Montenegro           False          False          False
Netherlands           True           True           True
Norway                True           True           True
Poland               False          False          False
~~~
{: .output}

## Select values or NaN using a Boolean mask.

*   A frame full of Booleans is sometimes called a *mask* because of how it can be used.

~~~
mask = subset > 10000
print(subset[mask])
~~~
{: .language-python}
~~~
             gdpPercap_1962  gdpPercap_1967  gdpPercap_1972
country
Italy                   NaN     10022.40131     12269.27378
Montenegro              NaN             NaN             NaN
Netherlands     12790.84956     15363.25136     18794.74567
Norway          13450.40151     16361.87647     18965.05551
Poland                  NaN             NaN             NaN
~~~
{: .output}

*   Get the value where the mask is true, and NaN (Not a Number) where it is false.
*   Useful because NaNs are ignored by operations like max, min, average, etc.

~~~
print(subset[subset > 10000].describe())
~~~
{: .language-python}
~~~
       gdpPercap_1962  gdpPercap_1967  gdpPercap_1972
count        2.000000        3.000000        3.000000
mean     13120.625535    13915.843047    16676.358320
std        466.373656     3408.589070     3817.597015
min      12790.849560    10022.401310    12269.273780
25%      12955.737547    12692.826335    15532.009725
50%      13120.625535    15363.251360    18794.745670
75%      13285.513523    15862.563915    18879.900590
max      13450.401510    16361.876470    18965.055510
~~~
{: .output}

## Group By: split-apply-combine

Pandas vectorizing methods and grouping operations are features that provide users 
much flexibility to analyse their data.

For instance, let's say we want to have a clearer view on how the European countries 
split themselves according to their GDP.

1.  We may have a glance by splitting the countries in two groups during the years surveyed,
    those who presented a GDP *higher* than the European average and those with a *lower* GDP.
2.  We then estimate a *wealthy score* based on the historical (from 1962 to 2007) values,
    where we account how many times a country has participated in the groups of *lower* or *higher* GDP

~~~
mask_higher = data > data.mean()
wealth_score = mask_higher.aggregate('sum', axis=1) / len(data.columns)
wealth_score
~~~
{: .language-python}
~~~
country
Albania                   0.000000
Austria                   1.000000
Belgium                   1.000000
Bosnia and Herzegovina    0.000000
Bulgaria                  0.000000
Croatia                   0.000000
Czech Republic            0.500000
Denmark                   1.000000
Finland                   1.000000
France                    1.000000
Germany                   1.000000
Greece                    0.333333
Hungary                   0.000000
Iceland                   1.000000
Ireland                   0.333333
Italy                     0.500000
Montenegro                0.000000
Netherlands               1.000000
Norway                    1.000000
Poland                    0.000000
Portugal                  0.000000
Romania                   0.000000
Serbia                    0.000000
Slovak Republic           0.000000
Slovenia                  0.333333
Spain                     0.333333
Sweden                    1.000000
Switzerland               1.000000
Turkey                    0.000000
United Kingdom            1.000000
dtype: float64
~~~
{: .output}

Finally, for each group in the `wealth_score` table, we sum their (financial) contribution
across the years surveyed using chained methods:

~~~
data.groupby(wealth_score).sum()
~~~
{: .language-python}
~~~
          gdpPercap_1952  gdpPercap_1957  gdpPercap_1962  gdpPercap_1967  \
0.000000    36916.854200    46110.918793    56850.065437    71324.848786   
0.333333    16790.046878    20942.456800    25744.935321    33567.667670   
0.500000    11807.544405    14505.000150    18380.449470    21421.846200   
1.000000   104317.277560   127332.008735   149989.154201   178000.350040   

          gdpPercap_1972  gdpPercap_1977  gdpPercap_1982  gdpPercap_1987  \
0.000000    88569.346898   104459.358438   113553.768507   119649.599409   
0.333333    45277.839976    53860.456750    59679.634020    64436.912960   
0.500000    25377.727380    29056.145370    31914.712050    35517.678220   
1.000000   215162.343140   241143.412730   263388.781960   296825.131210   

          gdpPercap_1992  gdpPercap_1997  gdpPercap_2002  gdpPercap_2007  
0.000000    92380.047256   103772.937598   118590.929863   149577.357928  
0.333333    67918.093220    80876.051580   102086.795210   122803.729520  
0.500000    36310.666080    40723.538700    45564.308390    51403.028210  
1.000000   315238.235970   346930.926170   385109.939210   427850.333420
~~~
{: .output}


> ## Selection of Individual Values
>
> Assume Pandas has been imported into your notebook
> and the Gapminder GDP data for Europe has been loaded:
>
> ~~~
> import pandas as pd
>
> df = pd.read_csv('data/gapminder_gdp_europe.csv', index_col='country')
> ~~~
> {: .language-python}
>
> Write an expression to find the Per Capita GDP of Serbia in 2007.
> > ## Solution
> > The selection can be done by using the labels for both the row ("Serbia") and the column ("gdpPercap_2007"):
> > ~~~
> > print(df.loc['Serbia', 'gdpPercap_2007'])
> > ~~~
> > {: .language-python}
> > The output is
> > ~~~
> > 9786.534714
> > ~~~
> >{: .output}
> {: .solution}
{: .challenge}

> ## Extent of Slicing
>
> 1.  Do the two statements below produce the same output?
> 2.  Based on this,
>     what rule governs what is included (or not) in numerical slices and named slices in Pandas?
> 
> ~~~
> print(df.iloc[0:2, 0:2])
> print(df.loc['Albania':'Belgium', 'gdpPercap_1952':'gdpPercap_1962'])
> ~~~
> {: .language-python}
> 
> > ## Solution
> > No, they do not produce the same output! The output of the first statement is:
> > ~~~
> >         gdpPercap_1952  gdpPercap_1957
> > country                                
> > Albania     1601.056136     1942.284244
> > Austria     6137.076492     8842.598030
> > ~~~
> >{: .output}
> > The second statement gives:
> > ~~~
> >         gdpPercap_1952  gdpPercap_1957  gdpPercap_1962
> > country                                                
> > Albania     1601.056136     1942.284244     2312.888958
> > Austria     6137.076492     8842.598030    10750.721110
> > Belgium     8343.105127     9714.960623    10991.206760
> > ~~~
> >{: .output}
> > Clearly, the second statement produces an additional column and an additional row compared to the first statement.  
> > What conclusion can we draw? We see that a numerical slice, 0:2, *omits* the final index (i.e. index 2)
> > in the range provided,
> > while a named slice, 'gdpPercap_1952':'gdpPercap_1962', *includes* the final element.
> {: .solution}
{: .challenge}

> ## Reconstructing Data
>
> Explain what each line in the following short program does:
> what is in `first`, `second`, etc.?
>
> ~~~
> first = pd.read_csv('data/gapminder_all.csv', index_col='country')
> second = first[first['continent'] == 'Americas']
> third = second.drop('Puerto Rico')
> fourth = third.drop('continent', axis = 1)
> fourth.to_csv('result.csv')
> ~~~
> {: .language-python}
>
> > ## Solution
> > Let's go through this piece of code line by line.
> > ~~~
> > first = pd.read_csv('data/gapminder_all.csv', index_col='country')
> > ~~~
> > {: .language-python}
> > This line loads the dataset containing the GDP data from all countries into a dataframe called 
> > `first`. The `index_col='country'` parameter selects which column to use as the 
> > row labels in the dataframe.  
> > ~~~
> > second = first[first['continent'] == 'Americas']
> > ~~~
> > {: .language-python}
> > This line makes a selection: only those rows of `first` for which the 'continent' column matches 
> > 'Americas' are extracted. Notice how the Boolean expression inside the brackets, 
> > `first['continent'] == 'Americas'`, is used to select only those rows where the expression is true. 
> > Try printing this expression! Can you print also its individual True/False elements? 
> > (hint: first assign the expression to a variable)
> > ~~~
> > third = second.drop('Puerto Rico')
> > ~~~
> > {: .language-python}
> > As the syntax suggests, this line drops the row from `second` where the label is 'Puerto Rico'. The 
> > resulting dataframe `third` has one row less than the original dataframe `second`.
> > ~~~
> > fourth = third.drop('continent', axis = 1)
> > ~~~
> > {: .language-python}
> > Again we apply the drop function, but in this case we are dropping not a row but a whole column. 
> > To accomplish this, we need to specify also the `axis` parameter (we want to drop the second column 
> > which has index 1).
> > ~~~
> > fourth.to_csv('result.csv')
> > ~~~
> > {: .language-python}
> > The final step is to write the data that we have been working on to a csv file. Pandas makes this easy 
> > with the `to_csv()` function. The only required argument to the function is the filename. Note that the 
> > file will be written in the directory from which you started the Jupyter or Python session.
> {: .solution}
{: .challenge}

> ## Selecting Indices
>
> Explain in simple terms what `idxmin` and `idxmax` do in the short program below.
> When would you use these methods?
>
> ~~~
> data = pd.read_csv('data/gapminder_gdp_europe.csv', index_col='country')
> print(data.idxmin())
> print(data.idxmax())
> ~~~
> {: .language-python}
>
> > ## Solution
> > For each column in `data`, `idxmin` will return the index value corresponding to each column's minimum;
> > `idxmax` will do accordingly the same for each column's maximum value.
> >
> > You can use these functions whenever you want to get the row index of the minimum/maximum value and not the actual minimum/maximum value.
> {: .solution}
{: .challenge}

> ## Practice with Selection
>
> Assume Pandas has been imported and the Gapminder GDP data for Europe has been loaded.
> Write an expression to select each of the following:
>
> 1.  GDP per capita for all countries in 1982.
> 2.  GDP per capita for Denmark for all years.
> 3.  GDP per capita for all countries for years *after* 1985.
> 4.  GDP per capita for each country in 2007 as a multiple of 
>     GDP per capita for that country in 1952.
>
> > ## Solution
> > 1:
> > ~~~
> > data['gdpPercap_1982']
> > ~~~
> > {: .language-python}
> >
> > 2:
> > ~~~
> > data.loc['Denmark',:]
> > ~~~
> > {: .language-python}
> >
> > 3:
> > ~~~
> > data.loc[:,'gdpPercap_1985':]
> > ~~~
> > {: .language-python}
> > Pandas is smart enough to recognize the number at the end of the column label and does not give you an error, although no column named `gdpPercap_1985` actually exists. This is useful if new columns are added to the CSV file later.
> >
> > 4:
> > ~~~
> > data['gdpPercap_2007']/data['gdpPercap_1952']
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Many Ways of Access
>
> There are at least two ways of accessing a value or slice of a DataFrame: by name or index.
> However, there are many others. For example, a single column or row can be accessed either as a `DataFrame`
> or a `Series` object.
>
> Suggest different ways of doing the following operations on a DataFrame:
> 1. Access a single column
> 2. Access a single row
> 3. Access an individual DataFrame element
> 4. Access several columns
> 5. Access several rows
> 6. Access a subset of specific rows and columns
> 7. Access a subset of row and column ranges
>
{: .challenge}
>
> > ## Solution
> > 1\. Access a single column:
> > ~~~
> > # by name
> > data["col_name"]   # as a Series
> > data[["col_name"]] # as a DataFrame
> >
> > # by name using .loc
> > data.T.loc["col_name"]  # as a Series
> > data.T.loc[["col_name"]].T  # as a DataFrame
> >
> > # Dot notation (Series)
> > data.col_name
> >
> > # by index (iloc)
> > data.iloc[:, col_index]   # as a Series
> > data.iloc[:, [col_index]] # as a DataFrame
> >
> > # using a mask
> > data.T[data.T.index == "col_name"].T
> > ~~~
> > {: .language-python}
> >
> > 2\. Access a single row:
> > ~~~
> > # by name using .loc
> > data.loc["row_name"] # as a Series
> > data.loc[["row_name"]] # as a DataFrame
> >
> > # by name
> > data.T["row_name"] # as a Series
> > data.T[["row_name"]].T as a DataFrame
> >
> > # by index
> > data.iloc[row_index]   # as a Series
> > data.iloc[[row_index]]   # as a DataFrame
> >
> > # using mask
> > data[data.index == "row_name"]
> > ~~~
> > {: .language-python}
> >
> > 3\. Access an individual DataFrame element:
> > ~~~
> > # by column/row names
> > data["column_name"]["row_name"]         # as a Series
> >
> > data[["col_name"]].loc["row_name"]  # as a Series
> > data[["col_name"]].loc[["row_name"]]  # as a DataFrame
> >
> > data.loc["row_name"]["col_name"]  # as a value
> > data.loc[["row_name"]]["col_name"]  # as a Series
> > data.loc[["row_name"]][["col_name"]]  # as a DataFrame
> >
> > data.loc["row_name", "col_name"]  # as a value
> > data.loc[["row_name"], "col_name"]  # as a Series. Preserves index. Column name is moved to `.name`.
> > data.loc["row_name", ["col_name"]]  # as a Series. Index is moved to `.name.` Sets index to column name.
> > data.loc[["row_name"], ["col_name"]]  # as a DataFrame (preserves original index and column name)
> >
> > # by column/row names: Dot notation
> > data.col_name.row_name
> >
> > # by column/row indices
> > data.iloc[row_index, col_index] # as a value
> > data.iloc[[row_index], col_index] # as a Series. Preserves index. Column name is moved to `.name`
> > data.iloc[row_index, [col_index]] # as a Series. Index is moved to `.name.` Sets index to column name.
> > data.iloc[[row_index], [col_index]] # as a DataFrame (preserves original index and column name)
> >
> > # column name + row index
> > data["col_name"][row_index]
> > data.col_name[row_index]
> > data["col_name"].iloc[row_index]
> >
> > # column index + row name
> > data.iloc[:, [col_index]].loc["row_name"]  # as a Series
> > data.iloc[:, [col_index]].loc[["row_name"]]  # as a DataFrame
> >
> > # using masks
> > data[data.index == "row_name"].T[data.T.index == "col_name"].T
> > ~~~
> > {: .language-python}
> > 4\. Access several columns:
> > ~~~
> > # by name
> > data[["col1", "col2", "col3"]]
> > data.loc[:, ["col1", "col2", "col3"]]
> >
> > # by index
> > data.iloc[:, [col1_index, col2_index, col3_index]]
> > ~~~
> > {: .language-python}
> > 5\. Access several rows
> > ~~~
> > # by name
> > data.loc[["row1", "row2", "row3"]]
> >
> > # by index
> > data.iloc[[row1_index, row2_index, row3_index]]
> > ~~~
> > {: .language-python}
> > 6\. Access a subset of specific rows and columns
> > ~~~
> > # by names
> > data.loc[["row1", "row2", "row3"], ["col1", "col2", "col3"]]
> >
> > # by indices
> > data.iloc[[row1_index, row2_index, row3_index], [col1_index, col2_index, col3_index]]
> >
> > # column names + row indices
> > data[["col1", "col2", "col3"]].iloc[[row1_index, row2_index, row3_index]]
> >
> > # column indices + row names
> > data.iloc[:, [col1_index, col2_index, col3_index]].loc[["row1", "row2", "row3"]]
> > ~~~
> > {: .language-python}
> > 7\. Access a subset of row and column ranges
> > ~~~
> > # by name
> > data.loc["row1":"row2", "col1":"col2"]
> >
> > # by index
> > data.iloc[row1_index:row2_index, col1_index:col2_index]
> >
> > # column names + row indices
> > data.loc[:, "col1_name":"col2_name"].iloc[row1_index:row2_index]
> >
> > # column indices + row names
> > data.iloc[:, col1_index:col2_index].loc["row1":"row2"]
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Exploring available methods using the `dir()` function
>
> Python includes a `dir()` function that can be used to display all of the available methods (functions) that are built into a data object.  In Episode 4, we used some methods with a string. But we can see many more are available by using `dir()`:
>
> ~~~
> my_string = 'Hello world!'   # creation of a string object 
> dir(my_string)
> ~~~
> {: .language-python}
>
> This command returns:
>
> ~~~
> ['__add__',
> ...
> '__subclasshook__',
> 'capitalize',
> 'casefold',
> 'center',
> ...
> 'upper',
> 'zfill']
> ~~~
> {: .language-python}
>
> You can use `help()` or <kbd>Shift</kbd>+<kbd>Tab</kbd> to get more information about what these methods do.
>
> Assume Pandas has been imported and the Gapminder GDP data for Europe has been loaded as `data`.  Then, use `dir()` 
> to find the function that prints out the median per-capita GDP across all European countries for each year that information is available.
>
> > ## Solution
> > Among many choices, `dir()` lists the `median()` function as a possibility.  Thus,
> > ~~~
> > data.median()
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}


> ## Interpretation
>
> Poland's borders have been stable since 1945,
> but changed several times in the years before then.
> How would you handle this if you were creating a table of GDP per capita for Poland
> for the entire twentieth century?
{: .challenge}


[pandas-dataframe]: https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.html
[pandas-series]: https://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.html
[numpy]: http://www.numpy.org/


---
title: "Plotting"
teaching: 15
exercises: 15
questions:
- "How can I plot my data?"
- "How can I save my plot for publishing?"
objectives:
- "Create a time series plot showing a single data set."
- "Create a scatter plot showing relationship between two data sets."
keypoints:
- "[`matplotlib`](https://matplotlib.org/) is the most widely used scientific plotting library in Python."
- "Plot data directly from a Pandas dataframe."
- "Select and transform data, then plot it."
- "Many styles of plot are available: see the [Python Graph Gallery](https://python-graph-gallery.com/matplotlib/) for more options."
- "Can plot many sets of data together."
---
## [`matplotlib`](https://matplotlib.org/) is the most widely used scientific plotting library in Python.

*   Commonly use a sub-library called [`matplotlib.pyplot`](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.html#module-matplotlib.pyplot).
*   The Jupyter Notebook will render plots inline by default.

~~~
import matplotlib.pyplot as plt
~~~
{: .language-python}

*   Simple plots are then (fairly) simple to create.

~~~
time = [0, 1, 2, 3]
position = [0, 100, 200, 300]

plt.plot(time, position)
plt.xlabel('Time (hr)')
plt.ylabel('Position (km)')
~~~
{: .language-python}

![Simple Position-Time Plot](../fig/9_simple_position_time_plot.svg)

> ## Display All Open Figures
> 
> In our Jupyter Notebook example, running the cell should generate the figure directly below the code. 
> The figure is also included in the Notebook document for future viewing.
> However, other Python environments like an interactive Python session started from a terminal 
> or a Python script executed via the command line require an additional command to display the figure.
>
> Instruct `matplotlib` to show a figure:
> ~~~
> plt.show()
> ~~~
> {: .language-python}
>
> This command can also be used within a Notebook - for instance, to display multiple figures
> if several are created by a single cell.
>
{: .callout}

## Plot data directly from a [`Pandas dataframe`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html).

*   We can also plot [Pandas dataframes](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.html).
*   This implicitly uses [`matplotlib.pyplot`](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.html#module-matplotlib.pyplot).
*   Before plotting, we convert the column headings from a `string` to `integer` data type, since they represent numerical values

~~~
import pandas as pd

data = pd.read_csv('data/gapminder_gdp_oceania.csv', index_col='country')

# Extract year from last 4 characters of each column name
# The current column names are structured as 'gdpPercap_(year)', 
# so we want to keep the (year) part only for clarity when plotting GDP vs. years
# To do this we use strip(), which removes from the string the characters stated in the argument
# This method works on strings, so we call str before strip()

years = data.columns.str.strip('gdpPercap_')

# Convert year values to integers, saving results back to dataframe

data.columns = years.astype(int)

data.loc['Australia'].plot()
~~~
{: .language-python}

![GDP plot for Australia](../fig/9_gdp_australia.svg)
## Select and transform data, then plot it.

*   By default, [`DataFrame.plot`](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.plot.html#pandas.DataFrame.plot) plots with the rows as the X axis.
*   We can transpose the data in order to plot multiple series.

~~~
data.T.plot()
plt.ylabel('GDP per capita')
~~~
{: .language-python}

![GDP plot for Australia and New Zealand](../fig/9_gdp_australia_nz.svg)
## Many styles of plot are available.

*   For example, do a bar plot using a fancier style.

~~~
plt.style.use('ggplot')
data.T.plot(kind='bar')
plt.ylabel('GDP per capita')
~~~
{: .language-python}

![GDP barplot for Australia](../fig/9_gdp_bar.svg)

## Data can also be plotted by calling the `matplotlib` `plot` function directly.
*   The command is `plt.plot(x, y)`
*   The color and format of markers can also be specified as an additional optional argument e.g., `b-` is a blue line, `g--` is a green dashed line.

## Get Australia data from dataframe

~~~
years = data.columns
gdp_australia = data.loc['Australia']

plt.plot(years, gdp_australia, 'g--')
~~~
{: .language-python}

![GDP formatted plot for Australia](../fig/9_gdp_australia_formatted.svg)

## Can plot many sets of data together.

~~~
# Select two countries' worth of data.
gdp_australia = data.loc['Australia']
gdp_nz = data.loc['New Zealand']

# Plot with differently-colored markers.
plt.plot(years, gdp_australia, 'b-', label='Australia')
plt.plot(years, gdp_nz, 'g-', label='New Zealand')

# Create legend.
plt.legend(loc='upper left')
plt.xlabel('Year')
plt.ylabel('GDP per capita ($)')
~~~
{: .language-python}

> ## Adding a Legend
> 
> Often when plotting multiple datasets on the same figure it is desirable to have 
> a legend describing the data.
>
> This can be done in `matplotlib` in two stages:
> 
> * Provide a label for each dataset in the figure:
>
> ~~~
> plt.plot(years, gdp_australia, label='Australia')
> plt.plot(years, gdp_nz, label='New Zealand')
> ~~~
> {: .language-python}
>
> * Instruct `matplotlib` to create the legend.
>
> ~~~
> plt.legend()
> ~~~
> {: .language-python}
>
> By default matplotlib will attempt to place the legend in a suitable position. If you
> would rather specify a position this can be done with the `loc=` argument, e.g to place
> the legend in the upper left corner of the plot, specify `loc='upper left'`
>
{: .callout}


![GDP formatted plot for Australia and New Zealand](../fig/9_gdp_australia_nz_formatted.svg)
*   Plot a scatter plot correlating the GDP of Australia and New Zealand
*   Use either `plt.scatter` or `DataFrame.plot.scatter`

~~~
plt.scatter(gdp_australia, gdp_nz)
~~~
{: .language-python}

![GDP correlation using plt.scatter](../fig/9_gdp_correlation_plt.svg)
~~~
data.T.plot.scatter(x = 'Australia', y = 'New Zealand')
~~~
{: .language-python}

![GDP correlation using data.T.plot.scatter](../fig/9_gdp_correlation_data.svg)

> ## Minima and Maxima
>
> Fill in the blanks below to plot the minimum GDP per capita over time
> for all the countries in Europe.
> Modify it again to plot the maximum GDP per capita over time for Europe.
>
> ~~~
> data_europe = pd.read_csv('data/gapminder_gdp_europe.csv', index_col='country')
> data_europe.____.plot(label='min')
> data_europe.____
> plt.legend(loc='best')
> plt.xticks(rotation=90)
> ~~~
> {: .language-python}
>
> > ## Solution
> >
> > ~~~
> > data_europe = pd.read_csv('data/gapminder_gdp_europe.csv', index_col='country')
> > data_europe.min().plot(label='min')
> > data_europe.max().plot(label='max')
> > plt.legend(loc='best')
> > plt.xticks(rotation=90)
> > ~~~
> > {: .language-python}
> > ![Minima Maxima Solution](../fig/9_minima_maxima_solution.png)
> {: .solution}
{: .challenge}

> ## Correlations
>
> Modify the example in the notes to create a scatter plot showing
> the relationship between the minimum and maximum GDP per capita
> among the countries in Asia for each year in the data set.
> What relationship do you see (if any)?
>
>
> > ## Solution
> > ~~~
> > data_asia = pd.read_csv('data/gapminder_gdp_asia.csv', index_col='country')
> > data_asia.describe().T.plot(kind='scatter', x='min', y='max')
> > ~~~
> > {: .language-python}
> >
> > ![Correlations Solution 1](../fig/9_correlations_solution1.svg)
> >
> > No particular correlations can be seen between the minimum and maximum gdp values
> > year on year. It seems the fortunes of asian countries do not rise and fall together.
> {: .solution}
>
> You might note that the variability in the maximum is much higher than
> that of the minimum.  Take a look at the maximum and the max indexes:
>
> ~~~
> data_asia = pd.read_csv('data/gapminder_gdp_asia.csv', index_col='country')
> data_asia.max().plot()
> print(data_asia.idxmax())
> print(data_asia.idxmin())
> ~~~
> {: .language-python}
> > ## Solution
> > ![Correlations Solution 2](../fig/9_correlations_solution2.png)
> >
> > Seems the variability in this value is due to a sharp drop after 1972.
> > Some geopolitics at play perhaps? Given the dominance of oil producing countries,
> > maybe the Brent crude index would make an interesting comparison?
> > Whilst Myanmar consistently has the lowest gdp, the highest gdb nation has varied
> > more notably.
> {: .solution}
{: .challenge}

> ## More Correlations
>
> This short program creates a plot showing
> the correlation between GDP and life expectancy for 2007,
> normalizing marker size by population:
>
> ~~~
> data_all = pd.read_csv('data/gapminder_all.csv', index_col='country')
> data_all.plot(kind='scatter', x='gdpPercap_2007', y='lifeExp_2007',
>               s=data_all['pop_2007']/1e6)
> ~~~
> {: .language-python}
>
> Using online help and other resources,
> explain what each argument to `plot` does.
>
> > ## Solution
> > ![More Correlations Solution](../fig/9_more_correlations_solution.svg)
> >
> > A good place to look is the documentation for the plot function -
> > help(data_all.plot).
> >
> > kind - As seen already this determines the kind of plot to be drawn.
> >
> > x and y - A column name or index that determines what data will be
> > placed on the x and y axes of the plot
> >
> > s - Details for this can be found in the documentation of plt.scatter.
> > A single number or one value for each data point. Determines the size
> > of the plotted points.
> {: .solution}
{: .challenge}

> ## Saving your plot to a file
> 
> If you are satisfied with the plot you see you may want to save it to a file,
> perhaps to include it in a publication. There is a function in the
> matplotlib.pyplot module that accomplishes this:
> [savefig](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.savefig.html).
> Calling this function, e.g. with
> ~~~
> plt.savefig('my_figure.png')
> ~~~
> {: .language-python}
> 
> will save the current figure to the file `my_figure.png`. The file format
> will automatically be deduced from the file name extension (other formats
> are pdf, ps, eps and svg).
>
> Note that functions in `plt` refer to a global figure variable
> and after a figure has been displayed to the screen (e.g. with `plt.show`) 
> matplotlib will make this  variable refer to a new empty figure.
> Therefore, make sure you call `plt.savefig` before the plot is displayed to
> the screen, otherwise you may find a file with an empty plot.
>
> When using dataframes, data is often generated and plotted to screen in one line,
> and `plt.savefig` seems not to be a possible approach.
> One possibility to save the figure to file is then to
>
> * save a reference to the current figure in a local variable (with `plt.gcf`) 
> * call the `savefig` class method from that variable.
>
> ~~~
> data.plot(kind='bar')
> fig = plt.gcf() # get current figure
> fig.savefig('my_figure.png')
> ~~~
> {: .language-python}
{: .callout}

> ## Making your plots accessible
>
> Whenever you are generating plots to go into a paper or a presentation, there are a few things you can do to make sure that everyone can understand your plots.
> * Always make sure your text is large enough to read. Use the `fontsize` parameter in `xlabel`, `ylabel`, `title`, and `legend`, and [`tick_params` with `labelsize`](https://matplotlib.org/2.1.1/api/_as_gen/matplotlib.pyplot.tick_params.html) to increase the text size of the numbers on your axes.
> * Similarly, you should make your graph elements easy to see. Use `s` to increase the size of your scatterplot markers and `linewidth` to increase the sizes of your plot lines.
> * Using color (and nothing else) to distinguish between different plot elements will make your plots unreadable to anyone who is colorblind, or who happens to have a black-and-white office printer. For lines, the `linestyle` parameter lets you use different types of lines. For scatterplots, `marker` lets you change the shape of your points. If you're unsure about your colors, you can use [Coblis](https://www.color-blindness.com/coblis-color-blindness-simulator/) or [Color Oracle](https://colororacle.org/) to simulate what your plots would look like to those with colorblindness.
{: .callout}
