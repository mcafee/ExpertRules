# EXPERT RULES

This repository contains the set of rules that can be used with McAfee Endpoint Security in the Exploit Prevention policy. 
The rules are classified into 2 major groups:

*1. MCAFEE* 
		- Contains the rules that are either authored by McAfee or derived from the Community authored expert rules. It contains different categories of Expert rules considering the purpose of the rule. All the rules within the *GENERIC_RULES* folder under *MCAFEE* can be considered as examples for learning.
		- These Expert rules in their current form have undergone validation for syntax, functionality and limited QA has been performed on a selected set of platforms. The rules are typically documented to provide details on the tested environment, links to techniques, limitations (if any), etc. Customer may further customize these template rules to suit their environment.
		
*2. COMMUNITY* 
		- Contains rules authored by Expert Rule Community
		- The Expert Rule community comprises of External Contributors to McAfee Endpoint Security product in terms of authoring Exploit Prevention Expert Rules. This comprises of Blue teamers, Customers, Security Professionals, SOC, etc.

*Note:*
McAfee recommends that all the Expert rules listed under *MCAFEE* and *COMMUNITY* repositories are validated on a non-production test environment based on the Customer's requirement. Customers should exercise caution in deploying the Expert rules in their environment. 
 
## Contributing

The repository license is Apache 2.0. Making a contribution to this repository means you are licensing the contribution under the repository license.

Pull requests are accepted and encouraged so users can share their approaches for detecting different events. For the benefit of the community, authors are required to document the rules with the fields described below and place them in the *COMMUNITY* folder. Pull requests have to contain a markdown file for each rule in the pull request with the following fields. Any pull requests not conforming to the below best practices will be rejected.

* **Title**: A short and descriptive title for the rule. e.g. *REMOTE FILE EXECUTION PROTECTION RULE*.

* **Author**: Here is the place to add the Author's details like the name, Company / organization, etc for the version of the Expert rule (starts from version 1.0). The modification to the rule will be recorded as an increment to the minor version along with the Author details.
For Example: Version 1.0 - <Author_name>, <Company/Organization_name>

* **Description**: A deep description of the purpose of the rule, techniques covered, stuff and actions that are supposed to be blocked by the use of the rule.

* **Rule TCL**: The rule TCL code that can be directly used in the *ENS Exploit Prevention* policy.  Something like:
```
Rule {
    Process {
        Include Match_Type { -v ... }
        Exclude Match_Type { -v ... }
    }
    Target {
        Match Match_Object {
            Include Match_Type { -v ... }
            Exclude Match_Type { -v ... }
            Include -access ...
        }
    }
}
```
Documentation for the rule language can be found [here](https://docs.mcafee.com/bundle/endpoint-security-v10-5-3-adaptive-threat-protection-expert-rules-syntax-reference/resource/PD27227.pdf).

* **Trigger**: Some steps to trigger the rule and verify that it actually works. You can put a reference here to any public and safe tool. 

* **Tested Platforms**: Provide the tested platform information like the OS version, OS architecture, Application name, Application version, Endpoint Security Product version, etc. 
For Example: OS: Windows 10 build 19041, Architecture: 64 bit, Application Name: Microsoft Edge, Application Version: 1.1.1.1, Endpoint Security version 10.7.0.1234

* **Notes**: Here is the place to add some clarifications related to the rule, how it works related to the OS, limitations (if any), references to any documentation that could help to understand it, etc.
