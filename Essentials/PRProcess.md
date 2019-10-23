# PR process

You finished working on your branch and now need someone to review your code.

## Creating my PR

1. The title should respect the convention `[(rider|driver|caboose|fluxdelux|core)] (TECH|Ticket number) What has changed in the PR`

Example :

* `[driver] TECH BUMP RxSwift to version 5.0`
* `[rider] OR-1234 Confirm pickup screen integration`

2. Fill the `Description` part with the Jira ticket link, a few sentences to describe what you changed and screenshots are also nice to have.

Example :

```
https://transcovo.atlassian.net/browse/OR-777

* Added some stuff
* Removed some stuff
```

3. Fill the `Where should the reviewer start ?` part with the most important files to check first.

Example :

```
* OrderCoordinator.swift
* OrderViewModel.swift
```

4. If possible, fill `How should this be manually tested ?` with steps to reproduce to test your changes.

Example :

```
1. Log in as a B2B user.
2. Switch profile.
3. Tap `Order now`.
```

6. Once you have created your PR, copy the link and type `pr <link to your PR>` in `#tech-pr-mobile` on Slack to notify other developers.

## During the review

If you need to do any correction to your PR, please create a new commit that contains only your PR fixes, it will be easier for the reviewer to see what has been updated.

## The review process

When your PR has been added to the pr bot, it's going to be reviewed:
* either by the daily pair reviewer team (1h every day, pairs are defined every monday for the coming week)
* or by anyone taking PR from the bot

Even if we have one pair of developers doing PR review every days it's really important that everyone is involved in the PR review process. The more people are involved in reviewing others PR the more effective this process becomes.

### Code owners

As the iOS team is growing quickly and we want developers from both the Supply and Passenger tribe to be able to review any pull request, we have recently enabled code owners functionality to the project. The aim is to ensure that we continue to share our coding practices and keep maximum consistency between the two applications. But we still want to have someone from the Passenger tribe to check PR concerning the passenger app and same for the driver app.

If you need a code owner validation the process is simple:
* if your PR affects the driver application, add it to the pr bot in the `#tech-supply-pr` slack channel
* if it affects the passenger application, add it to the pr bot in the `#tech-tribe-passenger` slack channel

