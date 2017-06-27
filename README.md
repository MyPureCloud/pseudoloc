# Pseudoloc

Pseudoloc aims to allow software developers to automatically generate pseudo-localized language strings in the normal course of their development workflow.

![Travis CI Build Status](https://travis-ci.org/MyPureCloud/pseudoloc.svg?branch=master)
[![Coverage Status](https://coveralls.io/repos/github/MyPureCloud/pseudoloc/badge.svg?branch=master)](https://coveralls.io/github/MyPureCloud/pseudoloc?branch=master)

## What?

Pseudoloc can help you automatically psuedo-localize your language strings. For example:

- Original English: `Genesys is Trusted by Over 10,000 Companies Globally`
- Pseudo-localized: `[‘İ球Gēńęśyş ĩś Trũştěd by Ovēr 10,000 Cōmpåņĭęś Glŏbâlly___________яش]`

## Why?

[Pseudo-localization](https://en.wikipedia.org/wiki/Pseudolocalization) of language strings aids discovery of UI display issues prior to the development and integration of translations. For example, translations may result in text expansion of 35%, and will introduce different character sets into the UI, which may cause layout and display bugs.
 
By allowing software developers to automatically generate pseudo-localized language strings, it opens the door to verify that the software will respond gracefully to translation and reduces the risk of the changes needing rework.

## How?
 
Pseudoloc integrates directly into your development workflow via an adapter module and a wrapper UI.

Pseudoloc provides a command-line interface which you can invoke however you like. Perhaps you attach it to a Save action in your favorite IDE? Perhaps you call it during your build script?

### Build

Assuming you have a Java 8 JDK and a recent version of Maven installed, do:

`$ mvn clean package`

### Run

```
$ java -jar cli/target/pseudoloc-cli-0.1-SNAPSHOT.jar
usage: pseudoloc <command> [ <args> ]

Commands are:
    help      Display help information
    android

See 'pseudoloc help <command>' for more information on a specific command.
```

See the [cli's README](cli/README.md) for more information.

## Modules

### Core

The [core](core/README.md) module contains the `Generator` and supporting classes which pseudo-localize language strings.

### Adapters

Adapters provide the integration needed to operate on the given platform's language strings.

- [adapter-android](adapter-android/README.md) - Android platform string resource integration 

### UI

- [cli](cli/README.md) - contains a command-line interface wrapping the adapters  

## Contributing

Contributions are welcome and encouraged!

Perhaps you have some improvements in mind for the core pseudo-localization algorithm?

Is your platform missing from the adapter list? Unless you're an Android developer, we don't have you covered yet, but we absolutely want to support other platforms.

Want to add a wrapper UI with tighter integration into your workflow? There are lots of possibilities.

Please see the [contributing guidelines](CONTRIBUTING.md) for more information.
