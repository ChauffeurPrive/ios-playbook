# Setup my work environment

1. Download the latest version of Xcode.
2. In the Terminal, install Bundler with `sudo gem install bundler`.
3. Run `git clone git@github.com:transcovo/iOS.git` to clone the project .
4. Run `make setup` in order to install all dependencies.
5. ☕️ time.
6. Open the `.xcworkspace`  of the rider or driver app.
7. Run the app.
8. If the app is running, you’re set to work on the project. 🎉

## Having an issue?

If you receive the following error during the install with the `nokogiri` package, it's probably because you have installed Xcode a while ago.
Just remove the `.bundle` directory in your home and rerun `make setup` should do the trick.

```bash
$ rm ~/.bundle
$ make setup
```
