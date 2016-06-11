# org-plaintext-rubybib
This is a short org-babel/ruby script (actually a code-block) that scans through an org-mode file for citations and uses citeproc-ruby to append a plaintext bibliography using the specified [csl](http://editor.citationstyles.org/about/) style. 

## What else you need

* Emacs / org-mode
* Ruby
* the [citeproc-ruby](https://github.com/inukshuk/citeproc-ruby) gem and its dependencies ([bibtex-ruby](https://github.com/inukshuk/bibtex-ruby))

## Also...

* a [Bibtex](http://www.bibtex.org) bibliography database of your own

# Excuses

As anyone who might chance on this can probably tell, I'm not a programmer and I don't really know what I'm doing ;) I am thus not really aware of whether this is 'the right solution' to this problem or not. 

My primary aim was to be able to preview the cited items in any paper I am writing in org-mode. I wasn't really expecting to be able to create a perfectly formatted and publishable bibliography, ulitmately I would leave that to the standard, more sophisticated tools (LaTeX/Bibtex/biber/biblatex etc)

# Use

Copy and paste the code block (from `#+NAME: create-bibliography` to `#+RESULTS: create-bibliography` into your org-mode buffer. 

Make sure you replace the dummy path-name in the following line ...

`cp.import BibTeX.open('/path/to/your/bibliography.bib').to_citeproc`

... with the path to your bibliography file.

Then place the cursor somewhere in the code-block and hit `C-c C-c`. Unless you've already change your settings otherwise you will be asked to give permission for the code-block to run, if you're happy that it's not doing anything naughty (it certainly shouldn't be!) then hit 'y' and within a second or two a new drawer names `RESULTS` should appear after the `#+RESULTS: create-bibliography` line, and it should be filled with your reference list.

# Finding citations

The script is set up to bibtex keys in the text of the file that contains it; my bibtex keys all follows the same basic pattern: |SOME LETTERS(maybe a 'dash' somewhere in there too)|A COLON|FOUR NUMBERS|MAYBE AN EXTRA LETTER|, and the regex in the line...

`res = content.scan(/[a-zA-Z\-]*:[0-9]{4}[a|b|c]?/)#collect regex matches`

... is set up to match this. You may have a different schema for your bibtex keys, in which case you'll have to change the regex to match.

