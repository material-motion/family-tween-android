# Material Motion Tween Family

[![Build Status](https://travis-ci.org/material-motion/family-tween-android.svg?branch=develop)](https://travis-ci.org/material-motion/family-tween-android)
[![codecov](https://codecov.io/gh/material-motion/family-tween-android/branch/develop/graph/badge.svg)](https://codecov.io/gh/material-motion/family-tween-android)
[![Release](https://img.shields.io/github/release/material-motion/family-tween-android.svg)](https://github.com/material-motion/family-tween-android/releases/latest)
[![Docs](https://img.shields.io/badge/jitpack-docs-green.svg)](https://jitpack.io/com/github/material-motion/family-tween-android/stable-SNAPSHOT/javadoc/)

The Tween Material Motion family provides a bridge between
[Property Animation](https://developer.android.com/guide/topics/graphics/prop-animation.html) and the
[Material Motion Runtime](https://github.com/material-motion/runtime-android).

## Features

`Tween` uses Property Animation's ObjectAnimator to animate a property along an easing curve.

Use a Tween like you would use a ObjectAnimator instance: provide a property, duration, and one or
both of the from/to value.

```java
Tween tweenBackgroundColor = new Tween<>(TweenProperty.BACKGROUND_COLOR, duration, Color.GREEN, Color.RED);
runtime.addPlan(tweenBackgroundColor, view);
```

Tween's properties map to the following ObjectAnimator properties:

| Tween | Property Animation |
|:-----:|:--------------:|
| delay  | startDelay |
| duration  | duration |
| from  | values... |
| property  | property |
| to  | values... |
| interpolator  | interpolator |

Learn more about the APIs defined in the library by reading our
[technical documentation](https://jitpack.io/com/github/material-motion/family-tween-android/2.1.0/javadoc/) and our
[Starmap](https://material-motion.github.io/material-motion/starmap/).

## Installation

### Installation with Jitpack

Add the Jitpack repository to your project's `build.gradle`:

```gradle
allprojects {
    repositories {
        maven { url "https://jitpack.io" }
    }
}
```

Depend on the [latest version](https://github.com/material-motion/family-tween-android/releases) of the library.
Take care to occasionally [check for updates](https://github.com/ben-manes/gradle-versions-plugin).

```gradle
dependencies {
    compile 'com.github.material-motion:family-tween-android:2.1.0'
}
```

For more information regarding versioning, see:

- [Material Motion Versioning Policies](https://material-motion.github.io/material-motion/team/essentials/core_team_contributors/release_process#versioning)

### Using the files from a folder local to the machine

You can have a copy of this library with local changes and test it in tandem
with its client project. To add a local dependency on this library, add this
library's identifier to your project's `local.dependencies`:

```
com.github.material-motion:family-tween-android
```

> Because `local.dependencies` is never to be checked into Version Control
Systems, you must also ensure that any local dependencies are also defined in
`build.gradle` as explained in the previous section.

**Important**

For each local dependency listed, you *must* run `gradle install` from its
project root every time you make a change to it. That command will publish your
latest changes to the local maven repository. If your local dependencies have
local dependencies of their own, you must `gradle install` them as well.

You must `gradle clean` your project every time you add or remove a local
dependency.

### Usage

How to use the library in your project.

#### Editing the library in Android Studio

Open Android Studio,
choose `File > New > Import`,
choose the root `build.gradle` file.

## Example apps/unit tests

To build the sample application, run the following commands:

    git clone https://github.com/material-motion/family-tween-android.git
    cd family-tween-android
    gradle installDebug

To run all unit tests, run the following commands:

    git clone https://github.com/material-motion/family-tween-android.git
    cd family-tween-android
    gradle test

## Guides

1. [How to animate a property with a Tween plan](#how-to-animate-a-property-with-a-tween-plan)
1. [How to animate a property with a keyframe Tween plan](#how-to-animate-a-property-with-a-keyframe-tween-plan)

### How to animate a property with a Tween plan

```java
Tween<Float> tween = new Tween<>(property, duration, from, to);
runtime.addPlan(tween, view);
```

### How to animate a property with a keyframe Tween plan

```java
float[] values = new float[] {0f, .5f, 1f};
float[] offsets = new float[] {0f, .25f, 1f};

Tween<Float> tween = new Tween<>(property, duration, values);
tween.offsets = offsets;
runtime.addPlan(tween, view);
```

## Contributing

We welcome contributions!

Check out our [upcoming milestones](https://github.com/material-motion/family-tween-android/milestones).

Learn more about [our team](https://material-motion.github.io/material-motion/team/),
[our community](https://material-motion.github.io/material-motion/team/community/), and
our [contributor essentials](https://material-motion.github.io/material-motion/team/essentials/).

## License

Licensed under the Apache 2.0 license. See LICENSE for details.
