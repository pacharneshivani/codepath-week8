# Week 8 Project: Pentesting Live Targets
Time spent: **4** hours spent in total
> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.
The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation
Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue
### Vulnerability #1: SQL injection ###

<img src='https://i.imgur.com/hs5tjfE.gif' title='SQL Injection' width='' alt='SQL Injection' />
In the Salesperson info page with the format "?id=XX" in the URL, when tested by adding a ' at the end of the URL, the red and green pages simply redirected, while the blue page showed an error message stating that the database query had failed. This gave away that the blue site had SQL Injection vulnerability, as shown in the GIF walkthrough.

### Vulnerability #2: Session Hijacking/Fixation ###

<img src='https://i.imgur.com/x7Ju3qE.gif' title='Session Hijacking' width='' alt='Session Hijacking' />
Using the target's session (that is logged in), the attacker can change his or her own session to match the target's so as to get the same login privileges.

## Green
### Vulnerability #1: User Enumeration ###

<img src='https://i.imgur.com/opBVKdl.gif' title='User Enumeration' width='' alt='User Enumeration' />
When using a non-existent username and a random password, the site's error message states "Log in was unsuccessful." However, when using an existing/valid username and a random password, it shows the same error message, but in bold.

### Vulnerability #2: Cross-Site Scripting ###

<img src='https://i.imgur.com/ozgeOZn.gif' title='User Enumeration' width='' alt='User Enumeration' />
This site's feedback form has a stored XSS alert vulnerability. The <script> tag and code entered is executed when the admin checks the feedback.

## Red
### Vulnerability #1: Insecure Direct Object Reference ###

<img src='https://i.imgur.com/VDLA67z.gif' title='Insecure Direct Object Reference' width='' alt='Insecure Direct Object Reference' />
The Salesperson database can be accessed by modifying the "?id=" tag in the URL; this can be used to access salespeople with ids 10 and 11, while the publicly displayed data ends at id 9.

### Vulnerability #2: Cross-Site Request Forgery ###

<img src='https://i.imgur.com/gT5JXmI.gif' title='Insecure Direct Object Reference' width='' alt='Insecure Direct Object Reference' />
The site accepts a post request from a different source that has a hidden form in it, and makes alterations to the user database.

## Assets
N/A

## Notes
N/A

## License
    Copyright [2017] [Shivani Pacharne]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
