[comment]: # "Auto-generated SOAR connector documentation"
# Playbook Utils

Publisher: Splunk Community  
Connector Version: 1\.1\.0  
Product Vendor: Splunk  
Product Name: SOAR  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 5\.2\.0  

This app provides utilities to interact with or get information about SOAR playbooks

[comment]: # " File: README.md"
[comment]: # "  Copyright (c) 2022 Splunk Inc."
[comment]: # "  Licensed under the Apache License, Version 2.0 (the 'License');"
[comment]: # "  you may not use this file except in compliance with the License."
[comment]: # "  You may obtain a copy of the License at"
[comment]: # "      http://www.apache.org/licenses/LICENSE-2.0"
[comment]: # "  Unless required by applicable law or agreed to in writing, software distributed under"
[comment]: # "  the License is distributed on an 'AS IS' BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND,"
[comment]: # "  either express or implied. See the License for the specific language governing permissions"
[comment]: # "  and limitations under the License."
[comment]: # ""
## Port Information

The app uses HTTP/ HTTPS protocol for communicating with the SOAR Rest APIs. Below are the default
ports used by Splunk SOAR.

|         Service Name | Transport Protocol | Port |
|----------------------|--------------------|------|
|         http         | tcp                | 80   |
|         https        | tcp                | 443  |


### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[get playbook tree](#action-get-playbook-tree) - Get details about the parent/child relationships of playbooks and actions  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'get playbook tree'
Get details about the parent/child relationships of playbooks and actions

Type: **generic**  
Read only: **True**

Note\: If the playbook\_run\_id parameter is not provided, it will attempt to asertain the playbook run that is calling the current app run\. If the action was not provied with a playbook\_run\_id and was called outside of a playbook, an error status will be returned\.

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**playbook\_run\_id** |  optional  | Playbook run ID of any playbook run in the tree that is to be retrieved \(If not provided and was called from a playbook, this defaults to the current playbook run id that initiated this app run\) | numeric | 
**include\_app\_runs** |  optional  | Include app runs in the playbook tree output | boolean | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.playbook\_run\_id | numeric | 
action\_result\.parameter\.include\_app\_runs | boolean | 
action\_result\.status | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 
action\_result\.data\.\*\.name | string | 
action\_result\.data\.\*\.type | string | 
action\_result\.data\.\*\.run\_id | numeric | 
action\_result\.data\.\*\.tree\_fill | string | 
action\_result\.data\.\*\.run\_details\.id | numeric | 
action\_result\.data\.\*\.run\_details\.misc\.scope | string | 
action\_result\.data\.\*\.run\_details\.misc\.parent\_playbook\_run | numeric | 
action\_result\.data\.\*\.run\_details\.owner | numeric | 
action\_result\.data\.\*\.run\_details\.status | string | 
action\_result\.data\.\*\.run\_details\.message | string | 
action\_result\.data\.\*\.run\_details\.version | numeric | 
action\_result\.data\.\*\.run\_details\.playbook | numeric | 
action\_result\.data\.\*\.run\_details\.cancelled | string | 
action\_result\.data\.\*\.run\_details\.container | numeric |  `phantom container id` 
action\_result\.data\.\*\.run\_details\.log\_level | numeric | 
action\_result\.data\.\*\.run\_details\.node\_guid | string | 
action\_result\.data\.\*\.run\_details\.test\_mode | numeric | 
action\_result\.data\.\*\.run\_details\.ip\_address | string |  `ip` 
action\_result\.data\.\*\.run\_details\.parent\_run | numeric | 
action\_result\.data\.\*\.run\_details\.start\_time | string | 
action\_result\.data\.\*\.run\_details\.update\_time | string | 
action\_result\.data\.\*\.run\_details\.\_pretty\_owner | string | 
action\_result\.data\.\*\.run\_details\.last\_artifact | numeric | 
action\_result\.data\.\*\.run\_details\.effective\_user | numeric | 
action\_result\.data\.\*\.run\_details\.\_pretty\_playbook | string | 
action\_result\.data\.\*\.run\_details\.\_pretty\_scm\_name | string | 
action\_result\.data\.\*\.run\_details\.\_pretty\_container | string | 
action\_result\.data\.\*\.run\_details\.\_pretty\_start\_time | string | 
action\_result\.data\.\*\.run\_details\.playbook\_run\_batch | string | 
action\_result\.data\.\*\.run\_details\.\_pretty\_update\_time | string | 
action\_result\.data\.\*\.run\_details\.\_pretty\_effective\_user | string | 
action\_result\.data\.\*\.tree\_prefix | string | 
action\_result\.data\.\*\.run\_details\.misc\.parent\_playbook\_run\.cb\_fn\_name | string | 
action\_result\.data\.\*\.run\_details\.misc\.parent\_playbook\_run\.child\_playbook\_id | numeric | 
action\_result\.data\.\*\.run\_details\.misc\.parent\_playbook\_run\.parent\_playbook\_id | numeric | 
action\_result\.data\.\*\.run\_details\.misc\.parent\_playbook\_run\.child\_playbook\_name | string | 
action\_result\.data\.\*\.run\_details\.misc\.parent\_playbook\_run\.parent\_playbook\_name | string | 
action\_result\.data\.\*\.run\_details\.misc\.parent\_playbook\_run\.parent\_playbook\_run\_id | numeric | 
action\_result\.data\.\*\.run\_details\.misc\.parent\_playbook\_run\.child\_playbook\_run\_name | string | 
action\_result\.data\.\*\.run\_details\.misc\.parent\_playbook\_run\.playbook\_run\_start\_time | numeric | 
action\_result\.data\.\*\.run\_details\.misc\.parent\_playbook\_run\.parent\_playbook\_run\_effective\_user\_id | numeric | 
action\_result\.data\.\*\.action | string | 
action\_result\.data\.\*\.status | string | 
action\_result\.data\.\*\.run\_details\.app | numeric | 
action\_result\.data\.\*\.run\_details\.asset | numeric | 
action\_result\.data\.\*\.run\_details\.action | string | 
action\_result\.data\.\*\.run\_details\.app\_name | string | 
action\_result\.data\.\*\.run\_details\.end\_time | string | 
action\_result\.data\.\*\.run\_details\.action\_run | numeric | 
action\_result\.data\.\*\.run\_details\.\_pretty\_app | string | 
action\_result\.data\.\*\.run\_details\.app\_version | string | 
action\_result\.data\.\*\.run\_details\.playbook\_run | numeric | 
action\_result\.data\.\*\.run\_details\.\_pretty\_asset | string | 
action\_result\.data\.\*\.run\_details\.\_pretty\_end\_time | string | 
action\_result\.data\.\*\.run\_details\.exception\_occured | boolean | 
action\_result\.data\.\*\.run\_details\.\_pretty\_action\_run | string | 
action\_result\.data\.\*\.run\_details\.\_pretty\_has\_widget | boolean | 
action\_result\.data\.\*\.run\_details\.\_pretty\_app\_directory | string | 
action\_result\.summary\.app\_run\_ids | numeric | 
action\_result\.summary\.playbook\_run\_ids | numeric | 
action\_result\.summary\.rendered\_playbook\_tree | string | 