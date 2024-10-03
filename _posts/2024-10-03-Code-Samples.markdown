---
layout: post
title: "Code Sample"
date: 2024-10-03 15:45:00 +0800
categories: jekyll update
permalink: /Intellij/Code-Sample
background: '/assets/images/banner.jpg'
language: "en"
item: post
menu-url: /Intellij
menu-title: IntelliJ Platform Plugin SDK
last-url: /Intellij/Code-of-Conduct
last-title: Code of Conduct
---

# Code Samples

This guide comes with a number of sample plugins available from dedicated intellij-sdk-code-samples GitHub repository.

Please see **README.md** which lists all available code samples with a short description.

Each sample is stored in a dedicated folder and is accompanied by its own **README.md**. Links to the corresponding tutorial or reference page in this tutorial, as well as a list of relevant show-cased elements are provided.

## Using Gradle

All sample plugins are based on Gradle, see Creating a Plugin Gradle Project to get started.

Additionally, the Working with Gradle in IntelliJ IDEA screencast offers a thorough introduction to Gradle functionality inside IntelliJ IDEA.

## Setting up Code Samples

Make sure plugins `Git`, `Gradle`, and `Plugin DevKit` are enabled.

`Plugin DevKit` plugin is bundled with IntelliJ IDEA until 2023.2.

> ##### Plugin DevKit Availability
> When using IntelliJ IDEA 2023.3 or later, the `Plugin DevKit` plugin must be installed from JetBrains Marketplace (Plugin Homepage) as it is no longer bundled with the IDE.

Clone the intellij-sdk-code-samples GitHub repository via **Git \| Clone....** After successful cloning, the IDE suggests opening the project.

Select the code sample(s) to import via the Gradle tool window.

Alternatively, import all code samples available by choosing **_gradleCompositeBuild**, which links all Gradle projects in a Composite Build.

After successful import, the project appears in the **Gradle** tool window tree as a new node.

Assign a Java 17 SDK in **Settings \| Build, Execution, Deployment \| Build Tools \| Gradle** for **Gradle JVM**.

Invoke **Reload All Gradle Projects** from the Gradle tool window toolbar if necessary.

## Running Code Samples

Run the plugin by using the Gradle `runIde` task shown under the corresponding project's **Tasks** node in the **Gradle** tool window.
