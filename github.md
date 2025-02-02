# 2. Setup _Git_ and _GitHub_

`Git` is a distributed version-control system for tracking changes in source code. A `repository` is where code lives, and the code from the prep course will live at [`ds-prep-course-2023`](https://github.com/LDSSA/ds-prep-course-2023) repository (basically where you are right now, reading this). All the learning materials and exercises will be released (made available) on this repository. You will learn more about `git` in the learning units 3 and 6.

### 2.1 Sign up for GitHub 

**Step 1:** [Sign up](https://github.com/join) for a `GitHub` account and follow the instructions.

**Step 2:** Open a terminal. Configure your email and username by running the 3 commands below. (**replace** `mig.dias.1212@gmail.com` below with the same email you used for github and `buedaswag` with your GitHub username).

```bash
git config --global user.email "mig.dias.1212@gmail.com"
git config --global user.username "buedaswag"
git config --global user.name "Bueda Swag"
```

### 2.2 Setup your workspace repository

The workspace directory/repository is where you will place everything you are working on, solve exercises, make changes to files, etc.

**Step 1:** Log into `GitHub`.

**Step 2:** In the upper-right corner of the page, click the "+" button and select `New repository`:

<img src='media/menu_create_repository.png' alt='Finder' width="75%" />

**Step 3:** Create a new **private** repository called `ds-prep-workspace`.

1. You need to explicitly select `Private` - this is your private work environment where nobody else will have access but you.

1. Initialize with a `README`.

1. Add a Python `.gitignore`. This file does exactly what it sounds like - it tells `git` which files to ignore when transfering files between your computer and `GitHub`.

<img src="https://user-images.githubusercontent.com/19359518/112880653-9ef76280-90c2-11eb-8768-00b2153756d5.png" alt='Finder' width="75%">

You can also check [Creating a new repository](https://help.github.com/en/articles/creating-a-new-repository) on GitHub for help.

### 2.3 Clone your workspace repository

Your workspace repository now exists on `GitHub`, but you also need a local copy (clone) on your computer. You will be working in the local repository and then transfer your work to your remote workspace repository on `GitHub`.

**Step 1:** Open a terminal (or use one you've already opened).

**Step 2:** Create a folder named `projects` by using the `mkdir` command. Don't feel intimidated by these commands. They are simply `bash` - a language to communicate with your operating system. `mkdir` essentially stands for **m**a**k**e **dir**ectory. The tilde symbol `~` is a shortcut address for your home directory.

```bash
mkdir ~/projects
```

**Step 3:** Enter the folder by using the `cd` command. Did you know that `cd` means **c**hange **d**irectory? So basically changing to a different folder.

```bash
cd ~/projects
```

**Step 4:** You can now **clone** (create a local copy of) the `ds-prep-workspace` repository you created on `GitHub`.
Replace `<username>` below with your `GitHub` username, removing the brackets `< >`, and run the command:

```bash
git clone https://github.com/<username>/ds-prep-workspace.git
```

   **Note**: if you have had a `GitHub` account since before this course and you are using `ssh keys` instead of `tokens`, first make sure that you have completed the steps starting [here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys), then clone your repository like this. You can skip step 5 and continue with section 2.4.

   ```bash
   git clone git@github.com:<username>/ds-prep-workspace.git
   ```

**Step 5:** You'll be asked for your `GitHub` username. Type it and press <kbd>enter</kbd>. Then you'll be asked for your git password. Passwords no longer work for `GitHub`, you will need to use `tokens`.

Go to <https://github.com/settings/tokens> and click on `Generate new token`. You can give it a name in the note field, such as `ldsa-token`. Then select `repo` in the scopes and click on `Generate token`. You will be shown a `token` you should save - **you will not be able to see it again after leaving that window**. 

Now use the `token` instead of your password and press <kbd>enter</kbd>

You should now have a local copy of your `ds-prep-workspace` in your `~/projects/ds-prep-workspace` folder.

<img src='media/personal_access_token.PNG' width="75%" />

### 2.4 Clone the `ds-prep-course-2023` repository

Let's clone the [`ds-prep-course-2023`](https://github.com/LDSSA/ds-prep-course-2023) repository. This is where all of the learning materials will be made available as the prep course progresses. You will be getting them (pulling) from there.

**Step 1:** Open a terminal (or use one you've already opened) and enter the `projects` folder:

```bash
cd ~/projects
```

**Step 2:** Clone the Prep Course repository (it's the same that contains the README you're reading right now!):

```bash
git clone https://github.com/LDSSA/ds-prep-course-2023.git
```

If you are using `ssh keys` for `GitHub`, use this command:

```bash
git clone git@github.com:LDSSA/ds-prep-course-2023.git
```

**Step 3:** Copy the contents of the local prep course repository to your local workspace repository. The `cp` bash command means **c**o**p**y. The `-r` stands for `recursive` and is necessary when you are copying folders (as opposed to files). Then you have the address of the folder that is being copied and to where it is copied.

```bash
cp -r ~/projects/ds-prep-course-2023/ ~/projects/ds-prep-workspace
```

And you're done with setting `Git` and `GitHub`! Go back to the main menu and continue with step 4, setting up the virtual environment.
