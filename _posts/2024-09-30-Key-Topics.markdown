---
layout: post
title: "Key Topics"
date: 2024-09-30 14:30:00 +0800
categories: jekyll update
permalink: /Intellij/Key-Topics
background: '/assets/images/banner.jpg'
language: "en"
item: post
menu-url: /Intellij
menu-title: IntelliJ Platform Plugin SDK
last-url: /Intellij/About-This-Guide
last-title: About This Guide
next-url: 
next-title: 
---

# Key Topics

The IntelliJ Platform is extensive and very capable, and its size and scope can initially be very daunting. This page is intended to list the key topics that a plugin author would be interested in, and provide quick links to the most common extension points.

## Essential Concepts

- Developing a Plugin.
- Testing Overview.
- Component model - the IntelliJ Platform is a component-based application and is responsible for creating components and injecting dependencies. Understanding this is necessary for building plugins.
- Extension Points - how to register components with extension points, and how to find out what extension points are available.
- Virtual Files - all file access should go through the Virtual File System, which abstracts and caches the file system. It means you can work with files that are on the local file system, in a zip file or are old versions from version control.

> See also Glossary for a handy reference of common terms.

## Code Model

The IntelliJ Platform's code model is called the PSI - the Program Structure Interface. The PSI parses code, builds indexes, and creates a semantic model.

## Common Extension Points

The IntelliJ Platform is extremely extensible, and most features and services can be extended. Some common extension points are:

- Actions - menu and toolbar items
- Code Inspections - code analysis that looks at the syntax trees and semantic models and highlight issues in the editor.
- Intentions - context-specific actions that are available in the Alt+Enter menu when the text caret is at a particular location.
- Code Completion.