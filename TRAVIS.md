## Running Tests on Travis

[Travis](https://travis-ci.org/) automatically runs tests whenever a github
repo changes.  To have Travis automatically run tests on your forked copy
of this repo:

1.  Fork this repo on [GitHub](https://github.com/).
1.  Visit the
    [Google Developers Console](https://console.developers.google.com/) and
    choose an existing project or create a new project.
1.  Under `APIs Manager`, enable `Google Cloud Container Builder API`
1.  Under `IAM & Admin`, choose `Service accounts`.
1.  Select `CREATE SERVICE ACCOUNT`, assign a name, and under Role,
    add `Project` > `Editor`
1.  Check `Furnish a new private key` so that a json credential file
    will be downloaded to your computer.
1.  Visit [Travis](https://travis-ci.org/profile ) and turn on Travis for your
    new forked repo.
1.  Go back to the [Travis](https://travis-ci.org/) home page, click on your
    repo, then click on `Settings`.
1.  Under Environment Variables, set `GOOGLE_PROJECT_ID` to the project id for
    the project you created or chose in step 2.
1.  Base-64 encode the json file you downloaded in step 5.  On unix machines,
    this can be done with a command like
    `base64 -w 0 < my-test-bf4af540ca4c.json`.
1.  Under Environment Variables, set `GOOGLE_CREDENTIALS_BASE64` to the
    base64-encoded json from step 7.  **Be sure te leave `Display value in build
    log` switched OFF.**
