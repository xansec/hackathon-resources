# Mayhem + GitHub Actions

In this exercise you will setup a GitHub Action that analyzes a toy project automatically everytime there is a push to the repository.

## Forking the repository

Before we begin, we first must fork the repository.

1. In your browser, navigate to https://github.com/makesoftwaresafe/mayhem-cmake-example.

2. Click "Fork" near the top of the page.

![Fork](assets/images/gh-click-fork.png)

3. When asked where you want to create the fork, select your username.

![Fork to Your Account](assets/images/gh-click-fork.png)

Now you have your own fork of the mayhem-cmake-example. Next, we'll clone and run the toy target locally.

## Clone and Run Locally

1. Clone the repo.

2. Create build directory, run cmake, make

3. Run the fuzz target.

## Add a Dockerfile

1. Modify the target and add our build commands.

2. Verify we can build locally.

3. Verify we can run locally.

## Add a Mayhemfile

1. Fill out "template" Mayhemfile.

## Setup your MAYHEM_TOKEN Repository Secret

1. Navigate to the settings page of your fork.

2. Expand the secrets drop down and select "Actions".

3. Click "New repository secret".

4. Under name enter "MAYHEM_TOKEN".

3. In another tab or window, open mayhem.forallsecure.com.

4. Copy your API Token

5. Paste into the "Value" field back in GitHub.

6. Click Add secret.

## Setup GitHub Action Workflow

1. Create .github/workflows directory.

2. Create a new mayhem.yml.

3. Copy the example from https://github.com/ForAllSecure/mcode-action-examples/blob/main/.github/workflows/mayhem.yml

4. Commit and Push to your fork.
