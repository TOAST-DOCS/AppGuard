## Security > AppGuard > Overview

AppGuard can help prevent code manipulation in application. AppGuard can also detect various tools to manipulate memory, speed, and code by pattern or heuristics, and restrict tools.

## Feature/Advantage

* Code manipulation can be prevented at the source.
* Various manipulation tools can be detected and restrict based on pattern or behavior that is difficult to bypass.
* AppGuard provide basis about restriction after check detected information by AppGuard through the Console.
* Powerful App protection with simple SDK linkage and easy app protection work.
* Is is applied to about 50 various services such as game, shopping, and easy payment, and is utilized for protecting

## Main Function

It provides the following function.

* Application protection via Web console provides convenient decompile protection function.
* Application manipulation detection through file integrity.
* Abusing environment detection like Rooting, Emulation, etc.
* Speed manipulation detection.
* Patterns and behavior based detection of various manipulation tools.
* It it not a manual restriction with a lot of resources by the operator, but a low-cose automatic restriction by the system. (to be provided in the near future)

## Service Terms

AppGuard uses the terms in [Table 1].

[Table 1] Service Terms of AppGuard

| Term       | Description                                                             |
| -------- | ----------------------------------------------------------------------- |
| Heuristic Detection      | Detection methods that can not be bypassed by detecting target like the cheat tools in the usual way |
| Code Manipulation        | Analyzing the code through decompilation, etc., and manipulating it for the purpose of obtaining the benefit |
| Decompile                | Converting compiled code into high-level language for easy analysis |
| File integrity           | Check if the original file has changed due to code manipulation, etc. |
| Rooting, Jail Break      | Raising the limited privileges of the smartphone to the higheste level of root privileges to allow unrestricted access to all parts of the system |
| Behavior Based Detection | A method of detecting using behavior of cheat tool or like to perform a cheat |
| Restriction System       | The restriction are automatically performed by the system, not by the operator through the detected logs, etc. |

## Service Structure

The structure of AppGuard is shown in [Figure 1].
After the code is linked (optional) to the app via the AppGuard SDK, use the Console or Command Line Interface(CLI) tools to complete protection work (required), then deploy app. The AppGuard Engine detects abusing and sends logs to the server for blocking or restriction.

![[Figure 1] The Structure of AppGuard Serivce](http://static.toastoven.net/toastcloud/static/common/img/cms_img/werebeta/img_06.jpg)
<center>[Figure 1] The Structure of AppGuard Serivce</center>
