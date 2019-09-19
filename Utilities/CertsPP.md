# Renew Development Certificates and Provisioning Profiles for Development 

Suppose that you have development certificate(s) that expire(s). As soon as it comes to you:

* Your Provisioning Profiles related to it (them) become unusable
* You have no possibility to deploy your daily basis code on test devices

Here the procedure to follow to renew all that "stuff".

## Procedure

1. Checkout Git Repository: `iOS-Certificates` (fastlane `match` repository handling all iOS Certificates / Provisioning Profiles)
2. Considering your environment (enterprise branch vs appstore branch), target the appropriate certificate(s) that are expired, and provisioning profiles related
3. Delete them manually and push the changes on the remote repository
4. Delete also manually all the Provisioning Profiles and Certificates related, on the iOS Dev Center
5. Run locally the following custom lane based on `match` fastlane command. You can copy paste it in `certificates.rb` file and access it by running `bundle exec fastlane` and select it among the other available lanes.

```ruby
desc "renew development certificates"
lane :renew_development_certificates do |_options|
  UI.message("Updating development provisioning profiles on the enterprise account...")
  match(
    git_branch: "##BRANCH_TO_TARGET##",
    type: "##TYPE##",
    app_identifier: [
      "##BUNDLE_IDENTIFIER_1##",
      "##BUNDLE_IDENTIFIER_2##"
    ],
    team_id: "##TEAM_ID##",
    force_for_new_devices: true,
    readonly: false,
    force: true
  )
end

```
## Parameters
* **\##BRANCH\_TO\_TARGET\##:** The targeted git branch on iOS-Certificates repository (`enterprise` vs `appstore`)
* **\##TYPE\##**: Three types of environment: `development`, `enterprise`, `appstore`
* **\##BUNDLE\_IDENTIFIER\##:** The bundle identifier for which you wish to generate another Provisioning Profile (`com.cp-driver.staging` for example)
* **\##TEAM_ID\##**: The Team ID referenced on iOS Dev Center, and under which the Provisioning Profile has been defined

## NB
_**Take good care of referencing appropriate bundle identifiers considering the environment on which you want to renew the Certificates / Provisioning Profiles.**_

_**Before wiping them from Git repository, identify which Provisioning Profiles and Certificates are related.**_

_**For enterprise / appstore environments, please consult an elder teammate of yours**_ 👴🏼


