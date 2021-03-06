# Radare2 Wiki
![repo size](https://img.shields.io/github/repo-size/securisec/radare2_wiki.svg) 

The goal of this wiki is to make a searchable collection of documents which can be used to find various use cases and help regarding using r2. This is a live wiki and the 
 goal is to updated frequently. If you have a tip, use case or plugin you would like to suggest, either create an issue, or tweet to me at [@securisec](https://twitter.com/securisec)

This wiki can be used either from the online version, local webapp or from the r2 shell. 

**Make sure to update the local version everytime before using. The wiki is updated frequently**

#### Credits:
Tons of great youtube videos, the radare2 irc channel, twitter, too many to list.
Wiki is powered by [wiki.js](https://wiki.js.org/) <img src="https://beta.requarks.io/svg/logo.svg" width="48">

## Online
The wiki is available online at [https://radare2.securisec.com](https://radare2.securisec.com)  
Both the online version and local version supports full search capability. The online version is always upto date. 

## Local webapp Installation
- Install wiki.js by following [these instructions](https://docs.requarks.io/wiki/install)
- Copy all the files in this repo to the `repo` directory, or run 
```git clone https://github.com/securisec/radare2_wiki.git repo/``` from inside your wiki directory.
- Allow some time for the search to finish indexing.

## Update local installation
- To update to the latest **(this wiki will be updated frequently :stuck_out_tongue_winking_eye:)**, simply run  
`git pull origin master` from inside the repo directory.

## r2pm
- This wiki can also be installed from r2pm using `r2pm -i r2wiki`

## From r2 shell
- Directions can be found in the [r2wiki.py](https://radare2.securisec.com/home/r2wiki-python)
> In order for this to work, you need a local copy of the wiki. You can get it from [github](https://github.com/securisec/radare2_wiki)
- The argument supports regex and the output is in less format

- Because the output is using less, you can highlight/search using `/` or show only matching lines by using `&`

- /path/to/repo/r2wiki.py needs to be absolute path {.is-warning}

- This can be accessed multiple ways. 
	- Method 1: Set an alias in your `~/.radare2rc` file		
    ```sh
    echo '$'wiki="#"'!'"pipe python /path/to/repo/r2wiki.py" >> ~/.radare2rc
    ```
	 > Invoke as `$wiki arg`
	- Method 2: Set an alias from inside r2 shell:
	```text
	$wiki=#!pipe python /path/to/r2wiki.py
	```
	 > invoke as `$wiki arg`
	- Method 3: 
    ```text
    #!pipe python /path/to/repo/r2wiki.py
    ```

## Tips for local wiki (applies to wiki.js version 1.0.12)
To style your local wiki in a manner similar to the online version, add the following to the `/wiki_installation_dir/server/views/layout.pug` under the section marked as `//- JS / CSS`  
 ```css
     style(type='text/css').
       .mkcontent {
         font-family: Arial;
       }

     style(type='text/css').
       .mkcontent {
         font-size: 16px;
       }
 ```
To change the search behaviour of your local wiki similar to that of the online version, change the following lines in `server/libs/search.js`
  ```
  - Line 73 to 1
  - Line 78 to 0
  - Line 88 to 3
  - Line 175 to 20
  ```
