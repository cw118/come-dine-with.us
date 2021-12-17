# Setting up come-dine-with.us locally

Welcome to the **come-dine-with.us** repo on GitHub! There are two "ways" of setting up our Flask app on your local device, both of which will require a GitHub account. **If you already know how to fork and clone this repo for local use, you may want to skip to one of the following sections**:

- [Flask: Installation and setting up a virtual environment](#flask-installation-and-setting-up-a-virtual-environment)
- [Setup for one-time use](#setup-for-one-time-use)
- [Setup for multi-time use](#setup-for-multi-time-use)

*If you're looking for the project description and links (ie. Devpost), see [README.md](README.md).*

### Cloning the repo locally

As mentioned previously, you will need a GitHub account to view and edit **come-dine-with.us** in a local development environment. If you're unfamiliar with `git` and `GitHub`, consider reading [MDN's Git and GitHub document](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/GitHub), or try [GitHub Docs](https://docs.github.com/en).

You'll also need to have [`Python`](https://www.python.org/downloads/) installed on your device (the latest version is recommended for Flask).

There are several options to setup a local copy of this repository. The choice is yours:
1. Install and use the [GitHub Desktop](https://docs.github.com/en/free-pro-team@latest/github/getting-started-with-github/github-desktop) app;
2. Install and use the [GitHub CLI](https://docs.github.com/en/free-pro-team@latest/github/getting-started-with-github/github-cli);
3. [Install `git`](https://git-scm.com/downloads) and use it from the
command line. Here are some helpful resources for `git`:

    - [GitHub Docs: Using Git](https://docs.github.com/en/get-started/using-git)
    - [GitHub Training: `git` cheatsheet](https://training.github.com/)

With one of the three choices provided just above, **first fork this repo** (piaoruilin/come-dine-with.us), *then* clone it to your local device.

### Flask: Installation and setting up a virtual environment

This doc will take you through setup using Command Prompt in Windows. If you if you are on macOS or Linux, or plan to use Bash or PowerShell, see [Flask Documentation: Installation](https://flask.palletsprojects.com/en/2.0.x/installation/?highlight=venv) and [Flask Documentation: Application Setup](https://flask.palletsprojects.com/en/2.0.x/tutorial/factory/#run-the-application).

**Note: You must have a local clone of this repository at this point.**

First, we will need to create and use a virtual environment (venv). **Navigate to the directory (folder) where your cloned version of the repo is stored** and type the following command:

```
> py -3 -m venv venv
```

Before working on the project, activate the virtual environment:

```
> venv\Scripts\activate
```

Your shell prompt will show the name of the activated environment, typically by prefixing `(venv)` before your directory path.

Now, **within the activated environment**, install Flask and the app's dependencies with these commands:

```
$ pip install Flask
$ pip install -r requirements.txt
```

Flask is now installed, along with the additional Flask packages and extensions used for the **come-dine-with.us** app!

## Setup for one-time use
There are a few things to setup before running the Flask app with the `flask` command in development mode (this mode shows an interactive debugger and restarts the server whenever changes in code are detected):

```
> set FLASK_APP=dine-with-us
> set FLASK_ENV=development
> flask run
```

You should see some output similar to the following:

```
* Serving Flask app "dine-with-us"
* Environment: development
* Debug mode: on
* Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
* Restarting with stat
* Debugger is active!
* Debugger PIN: 855-212-761
```

**Note:** Setting up with this method means you will have to manually set `FLASK_APP` and `FLASK_ENV` every time you kill your terminal. To avoid this, read the next section on "Setup for multi-time use".

## Setup for multi-time use

To run the Flask app multiple times across "different terminals" (meaning you kill your terminal at some point in development), we will still need to set `FLASK_APP` and `FLASK_ENV`. *If you only want or need to run app once, or you prefer to set up manually each time, go to [Setup for one-time use](#setup-for-one-time-use).*

This setup method is extremely simple: create a `.flaskenv` file in the root folder *(note that this file extension has been configured to be ignored by `Git` in `.gitignore`)*.

In your `.flaskenv` file, include the following lines:

```
FLASK_APP=dine-with-us
FLASK_ENV=development
```

And you're all set! You should be able to run the Flask app without a problem:

```
> flask run
```

Which should output something similar to the following:

```
* Serving Flask app "dine-with-us"
* Environment: development
* Debug mode: on
* Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
* Restarting with stat
* Debugger is active!
* Debugger PIN: 855-212-761
```

## Contributing to come-dine-with.us

Please note that **come-dine-with.us** was a hackathon project and will likely not be maintained by our team.
