# Creating a virtual environment

## Prompting virtual environment
In this book, we leveraged GenAI for every step of the SDLC, and installing a virtual environment is no exception. This task is a good candidate for using the agent mode within the GitHub Copilot chat window, with a prompt that follows the **Five S’s** discussed in detail in [Chapter 4](../ch4/).
### Best practices for crafting prompts for coding tasks
When working with GenAI applications for coding-related tasks, the best practices for crafting precise prompts can be summarized by the **five S’s**:

* **Structured** prompts with a clear separation between the instructions and provided data
* **Surrounding** information that provides context for the problem, such as the code language for the provided code and whether it compiles
* **Single-task** focus to ensure each prompt addresses only one objective
* **Specific** instructions detailing how the coding task should be performed, rather than using generic requests
* **Short and minimal** prompts that avoid fluff, redundant, or overly verbose instructions
  
A prompt to install our dependencies should include the following components:

1. **Python version**: Which version of Python should be used to run this project, in our case, it is Python 3.11.
2. **Environment tool**: Either venv or its alternatives.
3. **Requirements file**: The default is requirements.txt placed in the root of the project.
4. **Environment name**: A common practice is to name the environment .venv. We can also customize it to suit the project name with a prefix of a period, such as .supercharged.
5. **Environment location**: The library code is typically installed at the project root.
 
Considering these, here is an example of a prompt we can use with GitHub Copilot, either in PyCharm or VS Code:
```bash
CONTEXT: You are provided with:
1. Python version enclosed with {{{ VERSION }}}
2. Requirements file path enclosed with {{{ PATH }}}
3. Environment tool enclosed with {{{ TOOL }}}
4. Environment name enclosed with {{{ ENV NAME }}}
5. Location for the environment enclosed with {{{ Location }}}
TASK: Set up a virtual environment using the Python version, requirements file path, using the provided name and location for this project.
VERSION: {{{ Python 3.11 }}
PATH: {{{ requirements.txt }}}
TOOL: {{{ venv }}}
ENV NAME: {{{ .supercharged }}}
LOCATION: {{{ project root }}}
```
For reference, the output of the setup using agent mode with *GitHub Copilot* and the underlying *Claude Sonnet 4.0* specifies the steps for setting up an environment, activating it, and installing its dependencies.


For reference, here are the typical three shell commands we can use to manually install the virtual environment:
```bash
python3.11 -m venv .supercharged
source .supercharged/bin/activate
pip install -r requirements.txt
```


## Adding virtual environment to .gitignore
Since `requirements.txt` is sufficient for replicating the dependencies on any machine, there is no need to include the actual environment code in the repository. For that reason, it is best practice to ignore the installed dependencies. We can do this by adding the path of the installed requirements to the `.gitignore` file. We can chain another prompt in agent mode:
```bash
Add the environment path to .gitignore file.
```
This prompt successfully adds the path of the virtual environment to `.gitignore` .
If you named your environment differently, Copilot would likely add the correct name to the file. If you used `.supercharged` or `.venv`, no changes are required because these names are already in our files.

> ### Important Note
> Now that you are a supercharged coder, we encourage you to help your colleagues use these prompts when setting up a new virtual environment. These can be adapted for different environment tools, environment names, and projects, reducing the chances of errors when working with Agent mode


## Further reading
To learn more about the topics that were covered in this chapter, take a look at the following resources:

* Venv, virtual environment built-in: https://docs.python.org/3/library/venv.html
* Pipenv, dependency and environment management tools: https://pipenv.pypa.io/en/latest/
* Poetry, dependency and environment management tools: https://python-poetry.org/docs/dependency-specification/
* Conda, dependency and environment management tools: https://anaconda.org/anaconda/conda