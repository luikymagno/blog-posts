# Manage Dependencies with Poetry

In this post we will discuss Poetry: a tool for managing dependencies and packaging in Python projects. 

## What is Poetry?
Poetry helps you manage the dependencies during the development of Python-based projects and also build them easily. After you declare on which dependencies the software you are developing rely, it will install and update them for you. Additionally, Poetry have other nice features such as ensuring that installing your project in other environments won't cause any unwanted surprises. That means your project can be shared in a consistent manner and other people can run it with no major problems.

## How does it work?

### Installation
To install Poetry you could go through some easy steps manually, but its Dev team provided us a script that takes care of the whole process for you, so you just have to run it. You can find the link to the script in the Poetry website or directly here: https://install.python-poetry.org/.
Once you have run this script, you are good to go with Poetry.

### Basic usage
Here I'll show you what day-to-day use of Poetry would look like.
While reading this section, you will see that there is nothing too complicated, but there are some points worth paying attention to.

#### Create a virtual environment for your project
The first thing is to create a virtual environment for you project. By doing so, you garanty that what you in it won't affect your other projects. This is really important for many reasons. For instance, maybe you need to have different versions of the same library in different projects. Then, by creating a virtual environment for each project, you avoid having conflicts and, trust me, you had better avoid dependency conflicts.
To create a virtual environment, we will use pyenv https://github.com/pyenv/pyenv, but you can use any version management tool you want.

Create a directory for your project and go inside it
```
mkdir my-project | cd my-project
```

Install the Python version you want to use 
```
pyenv install 3.9.11
```

Create an environment called my_env_3911 with the Python version 3.9.11
As a good practice attach the Python version to the name of your environment
so you can easily remember it.
```
pyenv virtual-env my_env_3911 3.9.11
```

Running this command will create a file called .pyversion inside my-project. This file has the name of the virtual environment you are using, in our case my_env_3911. Then, every time
you enter my-project, my_env_3911 will be activated for you.
```
pyenv local my_env_3911
```

#### Set up Poetry
Now we will finally get into Poetry.

This first command initializes Poetry in your project. It will ask you some questions such as the project author's name. This information will be used for metadata.
After the command finishes, you notice two additional files in my-project.
The first one is pyproject.toml. This file will contain metadata about your project such as the author, description, license and some more. Also it will hold the name of the dependencies you will eventually add to your project and constraints on their versions as well.
The second file is the poetry.lock. As the name tells, it will be used to lock your project. How so? It will keep the exact version of each dependency of your project and then your project will locked to those specific versions. By doing so, Poetry ensures consistency when, for instance, several people are working on the same project which avoids breaks because of changes in dependencies.
Inside your my-project:
```
poetry init
```

Hereafter, when you want to declare a dependency for your project, you can simply run
```
poetry add library_name
```
This will install the dependency in the virtual environment you created before and update the pyproject.toml and poetry.lock files.

You can also remove dependencies with
```
poetry remove library_name
```

#### Poetry for an existing project
Let's say you downloaded a project that already uses Poetry, then it already has all set up (pyproject.toml, ...). To configure Poetry on your side you just have to create the virtual environment as before and run inside the project.
```
poetry install
```
Then all dependencies declared in the pyproject.toml and their exact versions (poetry.lock) will be installed for you.

## Conclusion
Poetry is a great tool and helps Python developers manage dependencies with ease and promotes consistency inside teams with several people working on the same projects.
Here we explored some of its features, but be aware that there many other that we didn't go over in this quick introduction. if you want to know more about Poetry and its advantages, check out the documentation https://python-poetry.org/

