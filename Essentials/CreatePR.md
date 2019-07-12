# Create a PR

You finished working on your branch and now need someone to review your code.

## Steps

1. Go to the iOS repository, `Pull requests` and click on `New pull request`.
2. Select `master` as `base` and your branch as `compare`.
3. Click on `Create pull request`.
4. Fill the `Description` part with the Jira ticket link, a few sentences to describe what you changed and screenshots are also nice to have.

Example :

```
https://transcovo.atlassian.net/browse/OR-777

* Added some stuff
* Removed some stuff
```

5. Fill the `Where should the reviewer start ?` part with the most important files to check first.

Example :

```
* OrderCoordinator.swift
* OrderViewModel.swift
```

6. If possible, fill `How should this be manually tested ?` with steps to reproduce to test your changes.

Example :

```
1. Log in as a B2B user.
2. Switch profile.
3. Tap `Order now`.
```

7. Click on `Create pull request`.
8. Copy the link to your PR and type `pr <link to your PR>` in `#tech-pr-mobile` on Slack to notify other developers.
