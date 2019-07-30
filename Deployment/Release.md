# Release the app
## Rider

## Driver
### When?
First monday of the sprint.

### Create release branch
In the iOS repository, you need to create a new branch release:

`bundle exec fastlane start_release --env driver`

We suggest you to deploy a staging build for the release in order to do the sanity check:

`bundle exec fastlane deploy_new_version envs:branch branch_name:driver/release/XXX --env driver`

### Sanity check
The sanity check is a series of manual tests that we need to run before each release in order to avoid regressions.


Tool: [TestRail](https://chpr.testrail.net/index.php?/plans/view/6709) (credentials are in 1Password)

1. Go to *Test Runs & Results*
2. Select *SANITY CHECK- DRIVER APP*
3. Click on *Edit*
4. Click on *Add Tests Run(s)*
5. Click on *select cases* for your new test run
6. Add a filter in the flags section with the pattern "driver sanity" and validate
7. Tap on *Configurations* in your test run and select *iOS* then click on *OK*
8. Finally, click on *Save Test Plan*

You can now select your new test run and process the sanity check.

### Deploy a build
You can now build the app and deploy it in all environments (staging, S3, store...), here is the command line:

`make deploy_driver_prod`

You can check your build status on the *#tech-ios-events* channel in Slack or bitrise.

### Release in the store
1. Go to [App Store Connect](https://appstoreconnect.apple.com/login)
2. Login with your account
3. Select the app: **Kapten Driver**
4. Create a new iOS version
5. Select your build
6. Update release note for all languages
7. Submit for review
8. For IDFA and encrypt questions, select *NO*

When the app has been reviewed you can deploy the app.

### AWS S3
Some drivers use an app stored in our S3. You need to specify that a new version is available in S3.

1. Go to AWS, S3 server and go to the driver prod folder (you can ask access to S3 by creating a JIRA ticket for the production team)
2. Edit the *meraki.plist* file
3. Update the values with your new release version
4. Edit *version.json* file
5. Replace the content by the one in the file *new_version.json*

### Update popup
Go to Rundeck and update an env variable in api-node (you can ask access to Rundeck by creating a JIRA ticket for the production team).

`APP_DRIVER_IOS_AVAILABLE` if the update you release is optional for the drivers.

`APP_DRIVER_IOS_REQUIRED` if the update you release is mandatory for the drivers.

