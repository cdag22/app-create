### SDLC Navigation

0. [Home](../../README.md)
1. Planning And Requirement Analysis
2. [Defining Requirements](../2_DefiningRequirements/README.md)
3. [Design and Architecture](../3_DesignAndArchitecture/README.md)
4. Building
5. Testing
6. Deployment
7. [Example Output](../7_ExampleOutput/README.md)
8. [Usage](../../FLAGS.md)

---

# 1. Planning and Requirement Analysis

## Product Feasibility

No tool exists for generating boilerplate code for web applications other than language specific instances that have limited or no customization available such as React's [create-react-app](https://github.com/facebook/create-react-app). If a highly customizable tool exist that was language agnostic it would aid:
- Those new to web development
- Those new to a serverside language, database, or framework
- Those looking to speedup and define a customizable application create process
- Those looking for best practices in the setup of a specific stack
- Those unfamiliar with the details of setting up a specific build process (e.g. Webpack config)
- Those looking to easily share a project stepup style or define a conistent project setup style in a streamlined fashion other than copying and pasting code

Bash may be a good language because it is supported on all Linux Distros, Mac OS (even though they are switching to Zsh as their default with their new OS Catalina. Since Mac OS is BSD UNIX, bash can be installed if ever removed from future versions of the OS), and can be installed on Windows 10 easily

## Quality Assurance Requirements

- Works on Mac OS, Windows 10, All Linux Distros.
- Does not require an specific language to be installed on the end users system (e.g. node/npm)
- Does not consume large amounts of RAM or CPU power when in use
- Highly customizable with commandline arguments
- Is throughly tested in the target language
- Is tested on all three variants of Operating Systems before deployment
- Can be packaged and built as installation file types such as ```.pkg``` (Mac OS) for Mac, Windows, and Linux. Alternatively, can be installed by all major OS package Managers as listed below:
	- WINDOWS: OneGet
	- MAC OS: Homebrew, Nix, MacPorts, pkgsrc
	- LINUX: apt, dpkg, RPM, Pacman, Gentoo, Zypper
