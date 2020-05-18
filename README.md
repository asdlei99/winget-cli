# Welcome to the Windows Package Manager Client (aka winget) repository

This repository contains the source code for the Window Package Manager Client (aka winget).

The packages available to the client are in the [Community repo](https://github.com/microsoft/winget-pkgs).

> The Windows Package Manager project is in Preview. We welcome all feedback, and that feedback might lead to big (maybe even breaking) changes.

## Installing the client

> The client requires Windows 10 1709 (build 16299) or later at this time.

### Microsoft Store [Recommended]

The client is distributed within the [App Installer](ms-windows-store://pdp/?productid=9nblggh4nns1) package. While this package is pre-installed on Windows, the client will not be made generally available during the Preview period. In order to get automatic updates from the Microsoft Store that contain the client, one must do one of the following:

* Install a [Windows 10 Insider](https://insider.windows.com/) build
* Join the Preview flight ring by sending a request to winget-feedback@microsoft.com

### Manually Update

The same Microsoft Store package will be made available via our [Releases](https://github.com/microsoft/winget-cli/releases). Note that installing this package will give you the WinGet client, but it will not enable automatic updates from the Microsoft Store.

> You may need to install the [Desktop Bridge VC++ v14 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=53175) and the associated Microsoft.VCLibs.140.00.UWPDesktop package.
> This should only be necessary on older builds of Windows if you get an error about missing framework packages.

### Build your own

You can also [build the client yourself](#building-the-client). While the client should be perfectly functional, we are not ready to provide full support for clients running outside of the official distribution mechanisms yet. Feel free to file an Issue, but know that it may get lower prioritization.

## Build Status

[![Build Status](https://dev.azure.com/ms/winget-cli/_apis/build/status/microsoft.winget-cli?branchName=master)](https://dev.azure.com/ms/winget-cli/_build/latest?definitionId=344&branchName=master)

## Overview

Our goal with the Windows Package Manager is to make your development process on Windows easier, faster, and more efficient. The goal isn't to be *the* package manager you use, but we do want to have all of the functionality to be a choice. And if you want to use a different package manager, we at least want to be able to provide you with a simple, quick command to bootstrap you into your preferred experience.

Although we are calling it a package manager because the term fits semantically, we don't actually manage what one would traditionally call a 'package'. Windows aleady has such a package manager; the MSIX deployment architecture is built around declarative, bundled packages that can cleanly be added and removed. However, there are many programs that have been written for Windows that are not in an MSIX package. We want to be able to manage these for you as well (as best we can).

For Preview, the goal is to get something usable in your hands as soon as possible. That means that right now we have the infrastructure to support install. From here, we have plenty of backlog features in our [Issues](https://github.com/microsoft/winget-cli/issues). You can upvote the ones you want, add more, or even [get started on one](https://github.com/microsoft/winget-cli/projects/1).

### Sources
The client is built around the concept of sources; a set of packages effectively. Sources provide the ability to discover and retreive the metadata about the packages, so that the client can act on it.

The default source reflects that data available from the [Community repo](https://github.com/microsoft/winget-pkgs).

We plan to better support additional sources, and additional types of sources, in the future. For now, additional sources can be configured, but only one used at a time.

## Building the client

### Prerequisites

* Windows 10 1709 (16299) or later
* [Developer Mode enabled](https://docs.microsoft.com/en-us/windows/uwp/get-started/enable-your-device-for-development)
* [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/)
   * Or use winget to install it ;) (although you may need to adjust the workloads via Tools->Get Tools and Features...)
* The following workloads:
   * .NET Desktop Development
   * Desktop Development with C++
   * Universal Windows Platform Development
* The following extensions:
   * [Microsoft Visual Studio Installer Projects](https://marketplace.visualstudio.com/items?itemName=VisualStudioClient.MicrosoftVisualStudio2017InstallerProjects)

### Building

We currently only build using the solution; command line methods of building a VS solution should work as well.

## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Data/Telemetry

This project collects usage data and sends it to Microsoft to help improve our products and services. See the [privacy statement](privacy.md) for more details.
