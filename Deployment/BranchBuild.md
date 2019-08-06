# Deploy a build from my branch

You finished implementing your feature or bug fix and you need to share it with QA or you simply want to test on a device.

## Steps

1. Open a terminal.
2. Either run `export BITRISE_TOKEN=<YOUR_BITRISE_TOKEN>` or add it to your shell rc file.
3. Run `bundle exec fastlane deploy_new_version envs:branch branch_name:"<BRANCH_NAME>" --env <APPLICATION_NAME>` where `BRANCH_NAME` is your branch name and `APPLICATION_NAME` is `driver` or `rider`.
4. A build has been triggered on Bitrise. :tada:
5. If you want to verify that it's the case, navigate to https://app.bitrise.io/dashboard/builds.
