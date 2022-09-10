# Atlas Network Development - Public View
![badge](https://img.shields.io/badge/owner-Swofty-important)
![badge](https://img.shields.io/badge/leads-Maploop%20%26%20Vespertilo-yellow)
[![badge](https://jitpack.io/v/Swofty-Developments/AtlasRedisAPI.svg)](https://jitpack.io/#Swofty-Developments/AtlasRedisAPI)
![badge](https://img.shields.io/badge/java%20version-v1.8.0-blueviolet)
![badge](https://img.shields.io/badge/developers-6-red)
[![badge](https://img.shields.io/discord/830345347867476000?label=discord)](https://discord.gg/atlasmc)
[![badge](https://img.shields.io/github/license/Swofty-Developments/AtlasRedisAPI)](https://github.com/Swofty-Developments/AtlasRedisAPI/blob/master/LICENSE.txt)

**[Official Discord](discord.gg/atlasmc)**

The official GitHub repository for the Atlas Network. This is where we host all of our libraries, main plugins, API wrappers, etc.

## Table of contents

* [Getting Started](#getting-started)
* [APIs and Libraries](#apis-and-libraries)
* [Content Deployment System](#content-deployment-system)
* [Pull Request Template](#pull-request-template)
* [How To Apply for Developer](#developer-application)
* [License](#license)

## Getting started

Currently, the only way to setup / start development for any project inside of this repository is to contact a Lead Developer or higher. You can find lead developers at the top of this page or go down to [Support](#support) to contact someone.

## APIs and Libraries

[![badge](https://jitpack.io/v/Swofty-Developments/AtlasRedisAPI.svg)](https://jitpack.io/#Swofty-Developments/AtlasRedisAPI)

All of our APIs / Libraries are under the same group-id as found below. None of our plugins currently use Gradle although we do currently support it. You will see the following inside of every single library / api that is listed under [Active Projects](#active-projects), just replace **VERSION** with the version of the release that is under that specific repository.

> Maven
```xml
<repositories>
    <repository>
        <id>jitpack.io</id>
        <url>https://jitpack.io</url>
    </repository>
</repositories>

<dependencies>
    <dependency>
        <groupId>com.github.AtlasNetworkDev</groupId>
        <artifactId>PROJECTNAME</artifactId>
        <version>VERSION</version>
    </dependency>
</dependencies>
```

> Gradle
```gradle
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}

dependencies {
    implementation 'com.github.AtlasNetworkDev:PROJECTNAME:VERSION'
}
```

## Content Deployment System

All of our core GitHub repositories make use of GitHub Actions, a feature that allows us to add extra checks / deploy your pull requests instantly. 
A guide for pushing to an Atlas repository can be [found by clicking on here](https://www.youtube.com/watch?v=UOBw3c8lv84), and even though a mini-run down of how the deployment system works is inside of the video, we'll also write it here;

- You cannot push straight to the master branch
- You can push to your branch as much as you want
- Once satisfied with your branch, you can open a pull request to merge your project into the master branch
- This pull request will trigger a variety of checks on your branch
- Assuming all of the checks pass, you will have to wait for 1 to 2 (number changes depending on the repo) lead developers to comment on your push and approve it
- After the approval count is met, you or anybody else will be able to accept the merge
- After your merge has been accepted, it will push all of your code into the master branch
- This will trigger the automatic deployment system, meaning that our deployment system will compile the master branch and push it to the servers
- You will then be able to view your deployment on our deployment tracker at [https://deployments.the-atlas.net](https://deployments.the-atlas.net)

## Pull Request Template

As described in the [Content Deployment System](#content-deployment-system) section of this guide - You will have to open a pull request to merge your branch into the master branch. For ease of use, and to ensure that your pull request gets accepted faster. We ask that you follow our pull request template contains all sections as follows;

### Describe Contents
Describe the contents of your pull request, with a full change-log like list of what you have implemented. You should link any and all Wiki articles about your push here.

### Risk Assessment
Think carefully about **how often the changed code is run** and **what the impact would be if that were to happen**. With that in mind, select from one of the following categories:

**No risk**
> Code that is not run in production (e.g. documentation and changes to tests).

**Low risk**
> Code where failures would affect a small proportion of requests/users (e.g. 1%). Failures would affect only a few low-traffic sections of Atlas (e.g. a single API endpoint, a single NPC, etc) or if the change failed we’d be in no worse a situation than we were before the change (e.g. attempting to reduce the number of database queries in a view).

**Medium risk**
> Code where failures would affect a medium proportion of requests/users (e.g. 10%). Failures would affect a significant number of users (e.g. Punishment System not working, Guild System offline) but could not bring down the entire server / site or make it unusable.

**High risk**
> Code where failures would affect most requests/users (e.g. >=50%) or could fail in such a way that the server / website as a whole is disabled. Failures would affect most users or core functionality (e.g. MongoDB connection, Redis framework) or result in problems with configuration of any shared resources.

If your change is _not_ high risk, make sure to explain how often the code will be run and if it does not affect production etc.

### Rollout / Rollback Plan

If your PR is **medium** or **high risk**, describe **how we'll know if something goes wrong with this code in production** and, if possible, **how we'll be able to quickly, safely disable it** in such a case (e.g. Vault variables, science experiments, feature flags, etc.). Document the specific information needed to put the plan into effect e.g if you're using a feature flag, make sure the name of the flag (or a link to its config page) is included.

### Credits

Describe who worked on each component of your push, and how much time all the contributors spent.

## Developer Application

To submit a developer application to the Atlas Network, please join our [discord](discord.gg/atlasmc) and follow the instructions found inside of our **#apply** channel.

## License
Atlas Network's GitHub is licensed under the permissive MIT license. Please see [`LICENSE.txt`](https://github.com/Swofty-Developments/AtlasRedisAPI/blob/master/LICENSE.txt) for more information.
