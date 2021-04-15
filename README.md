# Simple bash script for appending files to `.gitignore`

## Description

There are two ways. Ignore every listed file, ignore every file except listed ones. It's made so it does not duplicate files in `.gitignore`.

## How to install?

Installation is very simple. Clone this repo and place your script where you
want. I prefer to have it in my `/usr/bin`. You can set your
`CUSTOM_SCRIPT_NAME` while installing. I have it just as `ignore`.

```
git clone https://github.com/hllvc/gitignore.git
cd gitignore/
sudo chmod a+x ignore
sudo mv ignore /usr/bin/CUSTOM_SCRIPT_NAME
cd .. && rm -rf gitignore/
```

## How to use?

##### For demostration we will use script name as `ignore`!

Let's say we have directory with following files

```
myproject/
	main.tex
	main.log
	main.pdf
	main.aux
	pictures/
		pic1.jpg
		pic2.jpg
		pic3.jpg
```

and for example we want to ignore `main.log`, `main.pdf`, `main.aux`

#### Now there are two ways to use this script

1. All files added after `./ignore` as argument are appended to `.gitignore`.

```
ignore main.log main.pdf main.aux
```

2. If you pass `-e` as first argument and then files, everything but those files
   is ignored

```
ignore -e main.tex pictures
```

after executing eiter of theese, our `.gitignore` will look like.

```
main.log
main.pdf
main.aux
```

## Upcoming features

- check if files have been deleted and clean `.gitignore` of those files
- remove files from `.gitignore`
- simplify if there has been nesting within directories
