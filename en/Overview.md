## Security > AppGuard > Overview

AppGuard helps prevent manipulating application codes. It also detects and prohibits any tools which try to manipulate memory, speed or codes through patterned or heuristic method.

## Feature/Advantage

* Blocks code manipulation from the root stage.
* Detects and prohibits various fabricating tools through pattern- or act-oriented method.
* Checks information detected by AppGuard through Console so as to provide cause for restriction.
* Protects application with easy but strong means
* Currently in use for about 100 services, including game, shopping, and simple payment, to serve as a protective measure against abusive acts or application manipulation.

## Main Function

Functions are provided as follows:

* Easily blocks decompiling by protecting applications through web consoles
* Detects manipulated applications by checking integrity of files
* Detects abusive acts, such as rooting or emulation.
* Detects speed hack.
* Detects by pattern or act of each manipulative tool.
* Provides low-cost automatic sanctions, unlike resource-wasting manual system (to be updated soon)

## Glossary

For the AppGuard service, please refer to the glossary on Table 1.

[Table 1] Glossary for AppGuard

| Term       | Description                                                             |
| -------- | ----------------------------------------------------------------------- |
| Heuristic Detection      | A method of general detection on cheating tools which prevents taking a bypass |
| Code Manipulation        | A manipulative act by analyzing code decompiling to gain profits |
| Decompile                | An act of converting compiled codes to high-level language for easy analysis |
| File integrity           | An act of checking if original files are changed due to code manipulation |
| Rooting, Jail Break      | Upgrading smartphone user’s restricted authority to the highest root level so as to gain access to all system parts without a hitch |
| Behavior Based Detection | A method of detection by copying how a cheating tool does to cheat |
| System Restriction       | Sanctions on detected logs automatically posed by a system, not by an operator’s manual act |

## Service Structure

Figure 1 displays how AppGuard flows:
Using AppGuard’s SDK, the code is integrated with the application (optional), and then app protection service (required) is completed and deployed on a console or Command Line Interface (CLI). The AppGuard Engine sends a detective log to a server so as to block or sanction against abuses.

![[Figure 1] Flow of AppGuard](http://static.toastoven.net/prod_appguard/AppGuard_2_overview01_en.png)
<center>[Figure 1] Flow of AppGuard</center>
