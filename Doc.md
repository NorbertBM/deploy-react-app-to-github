# How to deploy a React application to github

Introduction
Creating websites and web applications ist just one parte of the web development procces. The website or web app is actualy done once it is live and working, and actualy acceseble to the public. Hi, my name is Norbert and in this tutorial, I am going to explore how to deploy a React application on GitHub pages.

For this I am going first create a starter react app and show you how you can deploy it and afterwords I am going to do the same thing for a real application.

I hope you are exited , and if you are then it would mean the world to me if you hit that like button and help the channel grow.

## What are GitHub pages?

GitHub Pages is a static website hosting service and it is free of charge.
It takes resources like HTML, CSS, and JavaScript files directly from the GitHub repository.
We can host our website on GitHub's with github.io domain or our own custom domain name.

## Types of GitHub Pages

There are three types of GitHub Pages sites which are,
User site
Project site
Organization site.

Project sites are connected to a specific project hosted on GitHub, such as a JavaScript library.
User and organization sites are connected to a specific GitHub account.
In this tutorial I am going to use my own user site

## User Site

The user site is connected to a specific GitHub account.
You should have a user account on GitHub.
To publish a user site, you must create a GitHub repo owned by your user account and repo name should be username.github.io. For Example, If your user name is TestName your repo name should be testname.github.io.

If you are not using any custom domain, then your website will be available at https://username.github.io.

## How to Publish the React application on GitHub Pages

To publish the user site, follow the below steps.

- Create an Account in GitHub. If you don't know how to create a GitHub then ples put a pin in this tutorial and checke out my tutorial on [how to create a GitHub account](https://youtube.com/).

- Create Repo in GitHub where the repo name should be username.github.io
- Create React Application.
- Deploy the React Application using GitHub Pages.
- Commit and Push the codebase (React Application) into GitHub repo.

## Step 1 - Create an Account in GitHub

- Open [GitHub link](https://github.com/)
- Create an account using your personal email

## Step 2 - Create Repo in GitHub

- Login to your GitHub account.
- Create the new repo by clicking the "+" icon at the right top of the page.
- Enter the repo name as yourusername.github.io and choose whether the repo should be public or private.
- Click on the "Create repository" button.

Now your repo has been created.

## Step 3 - Create React Application

Now lets create a generic react application which you want to host as a website.

`npx create-react-app my-app`

## Step 4 - Deploy the React Application

To deploy the application, follow the below steps.

1. Add GitHub Pages dependency package

Install "gh-pages" package using the below command.

`npm install gh-pages --save-dev`

In you package.json you should se now:

```
"devDependencies": {
    "gh-pages": "^3.2.3"
  }
```

_Version is variable!_

Makefile 2) Add homepage property to package.json file

Add the below property to your package.json file.

For a GitHub user site:
`"homepage": "https://{username}.github.io"`
For a custom domain:
"homepage": "https://testwebsite.com"

3. Add deploy scripts to package.json file

Add both "predeploy" and "deploy" property "scripts" to the package.json file as below,

```
"predeploy": "npm run build",
"deploy": "gh-pages -d build"

```

Makefile
The "predeploy" command is used to bundle the react application and the "deploy" command helps to deploy the bundled file.

4. Create a remote GitHub repository

Initialize the Git using "git init" command.
Add it as remote using "git remote add origin your-github-repository-url.git" command. 5) Deploy the Application to GitHub Pages

Now run the below command to deploy your react application to GitHub Pages.

npm run deploy
Makefile 6) Access deployed site

To get the published URL,

Go to your GitHub Repo.
Click Settings menu.

Go to the "Pages" Section.

You can see the "Your site is published" message.
Select branch to "gh-pages" and click on the "Save" button.

Now, you can access the deployed site using the published URL!

Step 5 - Commit and Push the codebase

Commit and push your code changes to the GitHub repo. It is an optional one. But, for maintaining the code base we can do this step.

git add .
git commit -m "commit message"
git push origin master
