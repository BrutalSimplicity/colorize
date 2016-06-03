Colorizer
=========

Syntax highlighter for code blocks in html. The general use case is for converting code in mardown generated html documents, but should work for any code embedded in `<pre>` or `<code>` tags.


# Usage

```text
> colorizer -h

usage: colorizer [options]

Add syntax highlighting to code in html. Built using Pygments.
http://pygments.org/

optional arguments:
  -h, --help            show this help message and exit
  -f HTMLFILE, --htmlfile HTMLFILE
                        The html file to process
  -s STYLE, --style STYLE
                        The style of syntax highlighting. See --list_styles
                        for a full list
  --list_styles         List of possible syntax styles to use
  -d DEFAULT, --default DEFAULT
                        Default lexer to use (i.e. csharp, python). See
                        --list_lexers or --find_lexer for a full list
  --list_lexers         List of lexers to choose from
  --find_lexer FIND_LEXER
                        Find a lexer
  --div_style DIV_STYLE
                        The inline css style to apply to the <div> tag
                        surrounding each code block (Ignored if --div_file is
                        used)
  --div_file DIV_FILE   The file to use as the inline css style to apply to
                        the <div> tag surrounding each code block
  -l, --linenos         Add line numbers to the code blocks
  -i, --inline          Create css styles inline on each tag as opposed to a
                        separate styles section
  -o OUT, --out OUT     Write results to this file
  --css_file CSS_FILE   Write code styles to this file. This still writes new
                        styles into the style tag (Ignored if --inline is
                        used)
  --log                 Log errors to "log.txt" in the same directory
```
