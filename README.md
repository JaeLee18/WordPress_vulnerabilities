# Project 7 - WordPress Pentesting
[embed src='https://youtube.com/embed/12345\x4svg onload=alert(1)\x3e'][\embed]
Time spent: **X** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. Title: WordPress <= 4.2.2 - Authenticated Stored Cross-Site Scripting (XSS)

  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough:
  <img src='http://i.imgur.com/mbazv3Q.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />
  - [ ] Steps to recreate: 
      Created a post using "Text" mode.
      Put following code in the page.

      " <a href="</a><a title=" onmouseover=alert('test')  ">link</a> ""

  - [ ] Affected source code:
    wp-includes/kses.php
    wp-includes/shortcodes.php
2. (Required)WordPress 3.6.0-4.7.2 - Authenticated Cross-Site Scripting (XSS) via Media File Metadata
  - [ ] Summary: The method wp_get_attachment_link() does not perform any output encoding
on the link text. Meta information from the audio file is used in the
link text, rendering wp_playlist_shortcode() vulnerable to Cross-Site
Scripting
    - Vulnerability types: XSS
    - Tested in version: 4.2.2
    - Fixed in version: 4.7.3
  - [ ] GIF Walkthrough: 
   <img src='http://i.imgur.com/ozrCApB.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />
  - [ ] Steps to recreate: 
  he following MP3 file can be used to reproduce this issue:

  https://www.securify.nl/advisory/SFY20160742/xss.mp3

  1) upload MP3 file to the Media Library (as Editor or Administrator).
  2) Insert an Audio Playlist in a Post containing this MP3 (Create Audio
  Playlist).
  - [ ] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/28f838ca3ee205b6f39cd2bf23eb4e5f52796bd7)
3. Title: WordPress  4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [ ] Summary: 
    - Vulnerability types:XSS
    - Tested in version:4.2.2
    - Fixed in version: 4.2.13
  - [ ] GIF Walkthrough: 
  <img src='http://i.imgur.com/icLCtIM.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />
  - [ ] Steps to recreate: 

    Make a post using following code with plain text mode.
    " [embed src='https://youtube.com/embed/12345\x3csvg onload=alert(12312313)\x3e'][/embed] "
  - [ ] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8)


1. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
1. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php) 

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [2017] [JaeJoong Lee]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
