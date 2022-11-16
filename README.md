<p align="left">
    <img src="https://img.shields.io/badge/go-v1.13-blue" alt="go badge">
    <img src="https://img.shields.io/badge/license-MIT-green" alt="MIT license badge">
    <a href="https://twitter.com/intent/tweet?text=https%3a%2f%2fgithub.com%2fgwen001%2fgithub-regexp%2f" target="_blank"><img src="https://img.shields.io/twitter/url?style=social&url=https%3A%2F%2Fgithub.com%2Fgwen001%2Fgithub-regexp" alt="twitter badge"></a>
</p>

# github-regexp

Basically a regexp over a GitHub search.

# Install

```
go install github.com/gwen001/github-regexp@latest
```

or

```
git clone https://github.com/gwen001/github-regexp
cd github-regexp
go install
```

# Usage

```
$ github-regexp -h

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

Feel free to [open an issue](/../../issues/) if you have any problem with the script.  

