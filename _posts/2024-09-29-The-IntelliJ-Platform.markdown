---
layout: post
title: "The IntelliJ Platform"
date: 2024-09-29 19:50:00 +0800
categories: jekyll update
permalink: /Intellij/The-IntelliJ-Platform
background: '/assets/images/banner.jpg'
language: "en"
item: post
menu-url: /Intellij
menu-title: IntelliJ Platform Plugin SDK
last-url: /Intellij/Home
last-title: Home
---

# The IntelliJ Platform

The IntelliJ Platform is not a product in and of itself but provides a platform for building IDEs. It is used to power JetBrains products such as IntelliJ IDEA. It is also Open Source and can be used by third parties to build IDEs, such as Android Studio from Google.

The IntelliJ Platform provides all the infrastructure that these IDEs need to provide rich language tooling support. It is a component-driven, cross-platform JVM based application host with a high-level user interface toolkit for creating tool windows, tree views, and lists (supporting fast search) as well as popup menus and dialogs.

The IntelliJ Platform has a full-text editor with abstract implementations of syntax highlighting, code folding, code completion, and other rich text editing features. An image editor is also included.

Furthermore, it includes open APIs to build standard IDE functionality, such as a project model and a build system. It also provides an infrastructure for a rich debugging experience, with language-agnostic advanced breakpoint support, call stacks, watch windows, and expression evaluation.

But the IntelliJ Platform's real power comes from the Program Structure Interface (PSI). It is a set of functionalities used to parse files, build rich syntactic and semantic models of the code, and build indexes from this data. PSI powers a lot of functionalities, from quick navigating to files, types, and symbols, to the contents of code completion popups and find usages, code inspections, and code rewriting, for quick fixes or refactorings, as well as many other features.

The IntelliJ Platform includes parsers and a PSI model for many languages, and its extensible nature means that it is possible to add support for other languages.

# Plugins

Products built on the IntelliJ Platform are extensible applications, with the platform being responsible for creating Extensions. The IntelliJ Platform fully supports plugins, and JetBrains hosts the JetBrains Marketplace, which can be used to distribute plugins that support one or more of the products. It is also possible to distribute plugins using a Custom Plugin Repository.

Plugins can extend the platform in many ways, from adding a simple menu item to adding support for a complete language, build system, and debugger. Many of the existing IntelliJ Platform features are implemented as plugins that can be included or excluded depending on the needs of the end product. See the Quick Start Guide for more details.

> ### Plugin Alternatives
> In some cases, implementing an actual IntelliJ Platform plugin might not be necessary, as alternative solutions exist.

# Open Source

The IntelliJ Platform is Open Source, under the Apache License, and hosted on GitHub.

While this guide refers to the IntelliJ Platform as a separate entity, there is no "IntelliJ Platform" GitHub repository. Instead, the platform is considered to be an almost complete overlap with the IntelliJ IDEA Community Edition, which is a free and Open Source version of IntelliJ IDEA Ultimate (the GitHub repository linked above is the JetBrains/intellij-community repository). Please note: starting with the 2021.1 release, some plugins bundled with IntelliJ IDEA Community Edition are not open-source.

The version of the IntelliJ Platform is defined by the version of the corresponding IntelliJ IDEA Community Edition release. For example, to build a plugin against IntelliJ IDEA (2019.1.1), build #191.6707.61 means specifying the same build number tag to get the correct IntelliJ Platform files from the intellij-community repository. See the Build Number Ranges page for more information about build numbers corresponding to version numbering.

Typically, an IDE that is based on the IntelliJ Platform will include the intellij-community repository as a Git submodule and provide configuration to describe which plugins from the intellij-community, and which custom plugins will make up the product.

# IDEs Based on the IntelliJ Platform

The IntelliJ Platform underlies many JetBrains IDEs. IntelliJ IDEA Ultimate is a superset of the IntelliJ IDEA Community Edition but includes closed-source plugins (see this feature comparison). Similarly, other products such as WebStorm and DataGrip are based on the IntelliJ IDEA Community Edition, but with a different set of plugins included and excluding other default plugins. This allows plugins to target multiple products, as each product will include base functionality and a selection of plugins from the IntelliJ IDEA Community Edition repository.

> Qualifying Open Source projects can apply for free licenses of JetBrains products.

The following IDEs are based on the IntelliJ Platform:

- JetBrains IDEs:
- - AppCode
- - Aqua
- - CLion
- - DataGrip
- - DataSpell
- - GoLand
- - IntelliJ IDEA
- - MPS
- - PhpStorm
- - PyCharm
- - Rider
- - RubyMine
- - RustRover
- - WebStorm
- - Writerside
- Android Studio IDE from Google
- Comma IDE for Raku (formerly known as Perl 6)
- Jmix Studio

### Rider

JetBrains Rider uses the IntelliJ Platform differently than other IntelliJ-based IDEs. It uses the IntelliJ Platform to provide the user interface for a C# and .NET IDE, with the standard IntelliJ editors, tool windows, debugging experience, etc. It also integrates into the standard Find Usages and Search Everywhere UI and uses code completion, syntax highlighting, and so on.

However, Rider doesn't create a full PSI (syntactic and semantic) model for C# files. Instead, it reuses ReSharper to provide language functionality. All the C# PSI model, inspections, code rewritings, such as quick fixes, and refactorings are run out of the process, in a command-line version of ReSharper. This means that creating a plugin for Rider involves two parts - a plugin that lives in the IntelliJ "front end" to show user interface, and a plugin that lives in the ReSharper "back end" to analyze and work with the C# PSI.

Fortunately, many plugins can simply work with the ReSharper backend. Rider takes care of displaying the results of inspections and code completion, and many plugins can be implemented without requiring an IntelliJ UI component.
