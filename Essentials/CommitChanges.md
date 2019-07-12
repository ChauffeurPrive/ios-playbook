# Commit my changes

When you commit your changes make sure to respect the commit message  validation regular expression `/\[(rider|driver|caboose|fluxdelux|core)\] (TECH|[A-Z]{2,5}-\d*|) ([\w\s]*)/`. Basically, you need to put the app/library name in square brackets (`[]`)  followed by `TECH` if it’s a technical task or the Jira ticket number and your custom message.

Examples of commit messages :

* [rider] OR-567 View model
* [driver] TECH Release
