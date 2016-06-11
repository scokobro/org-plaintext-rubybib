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

Then place the cursor somewhere between the two and hit `C-c C-c`. Unless you've already change your settinsg otherwise you will be asked to give permission for the code-block to run, if you're happy that it's not doing anything naughty (it certainly shouldn't!) then hit 'y' and within a second or two a new drawer names `RESULTS` should appera after the `#+RESULTS: create-bibliography` line.

