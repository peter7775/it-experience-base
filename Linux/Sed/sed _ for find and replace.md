### Find and replace text within a file using sed command

The procedure to change the text in files under Linux/Unix using sed:

Use Stream EDitor (sed) as follows:
`sed -i 's/old-text/new-text/g' input.txt`
The s is the substitute command of sed for find and replace
It tells sed to find all occurrences of ‘old-text’ and replace with ‘new-text’ in a file named input.txt
Verify that file has been updated:
more input.txt


### Syntax: sed find and replace text

The syntax is:
```
sed 's/word1/word2/g' input.file
## *bsd/macos sed syntax#
sed 's/word1/word2/g' input.file > output.file
sed -i 's/word1/word2/g' input.file
sed -i -e 's/word1/word2/g' -e 's/xx/yy/g' input.file
## use + separator instead of / ##
sed -i 's+regex+new-text+g' file.txt
```

The above replace all occurrences of characters in word1 in the pattern space with the corresponding characters from word2.
Examples that use sed to find and replace

Let us create a text file called hello.txt as follows:
```
$ cat hello.txt
The is a test file created by nixCrft for demo purpose.
foo is good.
Foo is nice.
I love FOO.
```

I am going to use s/ for substitute the found expression foo with bar as follows:
`sed 's/foo/bar/g' hello.txt`

Sample outputs:

```
The is a test file created by nixCrft for demo purpose.
bar is good.
Foo is nice.
I love FOO.
```


To update file pass the -i option:
`sed -i 's/foo/bar/g' hello.txt`
`cat hello.txt`

The g/ means global replace i.e. find all occurrences of foo and replace with bar using sed. If you removed the /g only first occurrence is changed:
`sed -i 's/foo/bar/' hello.txt`

The / act as delimiter characters. To match all cases of foo (foo, FOO, Foo, FoO) add I (capitalized I) option as follows:
sed -i 's/foo/bar/gI' hello.txt
`cat hello.txt`

Sample outputs:

```
The is a test file created by nixCrft for demo purpose.
bar is good.
bar is nice.
I love bar.
```

### sed command problems

Consider the following text file:
`$ cat input.txt`
http:// is outdate.
Consider using https:// for all your needs.

Find word ‘http://’ and replace with ‘https://www.cyberciti.biz’:
`sed 's/http:///https://www.cyberciti.biz/g' input.txt`

You will get an error that read as follows:

sed: 1: "s/http:///https://www.c ...": bad flag in substitute command: '/'

Our syntax is correct but the / delimiter character is also part of word1 and word2 in above example. Sed command allows you to change the delimiter / to something else. So I am going to use +:
`sed 's+http://+https://www.cyberciti.biz+g' input.txt`

Sample outputs:

```
https://www.cyberciti.biz is outdate.
Consider using https:// for all your needs.
```

### How to use sed to match word and perform find and replace

In this example only find word ‘love’ and replace it with ‘sick’ if line content a specific string such as FOO:
`sed -i -e '/FOO/s/love/sick/' input.txt`

Use cat command to verify new changes:
cat input.txt
Recap and conclusion – Using sed to find and replace text in given files

The general syntax is as follows:
```
## find word1 and replace with word2 using sed ##
sed -i 's/word1/word2/g' input
## you can change the delimiter to keep syntax simple ##
sed -i 's+word1+word2+g' input
sed -i 's_word1_word2_g' input
## you can add I option to GNU sed to case insensitive search ##
sed -i 's/word1/word2/gI' input
sed -i 's_word1_word2_gI' input
```
* * *

/ Vivek Gite  - https://www.cyberciti.biz/faq/how-to-use-sed-to-find-and-replace-text-in-files-in-linux-unix-shell/