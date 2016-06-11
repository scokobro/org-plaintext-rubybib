# org-plaintext-rubybib
This is a short org-babel/ruby script that scans through an org-mode file for citations and uses citeproc-ruby to append a plaintext bibliography using the specified csl style. 

## What else you need

* Emacs / org-mode
* Ruby
* the [citeproc-ruby](https://github.com/inukshuk/citeproc-ruby) gem and its dependencies ([bibtex-ruby](https://github.com/inukshuk/bibtex-ruby))

## Also...

* a [Bibtex](http://www.bibtex.org) bibliography database of your own

# Excuses

As anyone who might chance on this can probably tell, I'm not a programmer and I don't really know what I'm doing ;) I am thus not really aware of whether this is 'the right solution' to this problem or not. 

My primary aim was to be able to preview the cited items in any paper I am writing in org-mode. I wasn't really expecting to be able to create a perfectly formatted and publishable bibliography, ulitmately I would leave that to the standard, more sophisticated tools (LaTeX/Bibtex/biber/biblatex etc)


