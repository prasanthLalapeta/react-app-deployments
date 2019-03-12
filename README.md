<h1 align="center">
<br>
  <a href="https://github.com/prasanthLalapeta/react-app-deployments"><img src="https://techstream.org/images/img/Final-steps-with-React-JS-App.jpg" alt="Deploying React App in various environments Every Developer Should Know" width=200"></a>
  <br>
    <br>
  Deploying React App in various environments - Every Developer Should Know
  <br><br>
</h1>


## Introduction

This repository was created with the intention of helping developers regarding how to deploy react apps in various environments. It is not a requirement, but a guide for better developers.

## AWS S3 - 7-Step Deployment Process:

**Step 1:** Run `npm run` to install dependencies, then `npm run build` to create the ./build folder

**Step 2:** Login to your AWS S3 account. Click on `Services` followed by `S3` in the dropdown.

**Step 3:** Click on Create Bucket and fill out both your Bucket Name and Region (for the USA we recommend US Standard). Click Create to create your bucket.

**Step 4:** Open the `Permissions` tab and deselect all block options and save.

**Step 5:** Goto `Properties` tab and click on `Static Website Hosting` card where you should see the URL (or endpoint) of your website (ie. example. http://react-build-test.s3-website-us-east-1.amazonaws.com/). Click Enable website hosting and fill in both the Index document and Error document input fields with `index.html`. Click Save.

**Step 6:** Click on your new S3 bucket by pressing `Overview` tab to open the bucket. Click Upload and select all the files within your ./build folder. Click Start Upload. Once the files are done, select all of the files, right-click on the selected files (or click on the Actions button) and select Make Public.

**Step 7:** Click on the Properties tab, open Static Website Hosting, and click on the Endpoint link. The app should be running on that URL.

- **[√] Working Sample:** http://react-build-test.s3-website-us-east-1.amazonaws.com/


## Heroku - 7-Step Deployment Process:

**Step 1:** Create a `Procfile` with the following line: `web: npm run start:prod`. We do this because Heroku runs `npm run start` by default, so we need this setting to override the default run command.

**Step 2:** Add `"heroku-postbuild": "npm run build"` line to your `package.json` file in the `scripts` area. So that Heroku can build your production assets when deploying.

**Step 3:** Add `"prebuild": "npm run build:clean"` line to your `package.json` file in the `scripts` area. So that Heroku will empty build folder before triggering build.

**Step 4:** Login to your `heroku` account and click on Create new app and fill out your app name. Click Create to create your app.

**Step 5:** Go to `Settings` tab and navigate to `Buildpacks` section and click `Add buildpack` and select `nodejs`

**Step 6:** Go to `Deploy` tab and navigate to `Deployment method` section and select `GitHub` and click `Connect to GitHub` follwed by authorization to grant permission, So that each and everytime you made changes to your github repo will be automatically to heroku for triggering latest build.

**Step 7:** Click on the app you just created in heroku, click `open app`. The app should be running on that URL.

- **[√] Working Sample:** https://react-build-test.herokuapp.com/

## Contributions

Feel free to submit a PR adding a code and steps for your own environment :raised_hands: :muscle:. Please feel free to do so.

Thanks!
