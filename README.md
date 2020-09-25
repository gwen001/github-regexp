# github-regexp

Basically a regexp over a GitHub search.


# Warning

This repository is not public yet.
If you get access it means that you're part of the GitHub sponsors program.
For now, you're not allowed to release it, publish it or give access to anyone else.

Please remember that this program is still under development, bugs and changes may occur.


# Install

```
go get -u github.com/gwen001/github-regexp
```

or

```
git clone https://github.com/gwen001/github-regexp
cd github-regexp
go install
```


# Usage

```
github-regexp -h

Usage of github-regexp:
  -i	force the regexp to be case insensitive
  -k	exit the program when all tokens have been disabled
  -r string
    	regexp to search, default is SecLists secret-keywords list
  -s string
    	search term you are looking for (required)
  -t string
    	github token (required), can be:
    	  • a single token
    	  • a list of tokens separated by comma
    	  • a file containing 1 token per line
    	if the options is not provided, the environment variable GITHUB_TOKEN is readed, it can be:
    	  • a single token
    	  • a list of tokens separated by comma
```

If you want to use multiple tokens, you better create a `.tokens` file in the executable directory with 1 token per line  
```
token1
token2
...
```
or use an environment variable with tokens separated by comma:  
```
export GITHUB_TOKEN=token1,token2...
```

Tokens are disabled when GitHub raises a rate limit alert, however they are re-enable 1mn later.
You can disable that feature by using the option `-k`.

<img src="https://github.com/gwen001/github-regexp/raw/master/preview.png">


# Todo

- fix the output bug when the file is only 1 line (strpos)
- change the order of the extra searches ?
- ?


# Changelog

**25/09/2020**
- quick mode added
- tokens can be read from any file

**23/09/2020**
- fixed an issue in the api call (params name)
- added binary

**13/08/2020**
- fixed some types & output bugs

**06/08/2020**
- disabled languages and noise searches
- added an option to display urls only
- added an option to display only the matched parts
- added an option to force the regexp to be case insensitive
- creation


---

Feel free to ping me on Twitter if you have any problem to use the script.  
https://twitter.com/gwendallecoguic
