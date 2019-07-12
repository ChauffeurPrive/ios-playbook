# Translate my content

You are implementing your feature but you need to translate some content in the different locales supported by the app.

## Prerequisite

* Access to the BackOffice.

## Steps

1. Go to the production BackOffice and navigate to `Configuration > Translation Keys`  or click on this [link](https://bo.kapten.com/translation_keys).
2. Click on the `Create translation key` button on the left.
3. A modal should appear where you can enter the :
	1. `Key` : This is what you are going to use with the localisation dependency in the code. It’s shared between iOS and Android.
	2. `English Content` : What the text should be in English.
	3. `Tags` : The tags related to the key. It’s usually `iOS` and `Android`.
	4. `Project` : The project related to the key. It’s usually `CP rider app` or `CP driver app`.
	5. `Description` : A description of what is translated by the key. For example it can be the title of a screen or the text of a button.
	6. `Has Plural` : If your text has a plural, leave it as `Yes`, otherwise change it to `No`.
	7. `English Content (Plural)` : If your text has a plural, this is where you will put it. For example if a key is translating `ride`, maybe you will need to use the plural `rides`.
4. Fill the informations and check the `create another key` checkbox if you need to create other translations keys, it will pre-fill the tags and project for the next keys so you don’t have to do it each time. Once you are done, click on `Save`.
5. Now that you have created the translations keys, ask your Product Manager to request the translations in the locales supported by the app.
6. Once it’s done, open a terminal and run `make pull_rider_localization` or `make pull_driver_localization`  to fetch the translations from PhraseApp which is what we use at Kapten for translations.
7. Now that you are all set up, you can use your translations keys in your view models which is the usual place for them with the `LocalizationType` dependency.

Example of usage :

```swift
dependencies.localization.localize(key: "my_key")
```
