Colorizer
=========

Syntax highlighter for detecting and highlighting code blocks in html. The general use case is for converting code in markdown-generated html documents, but should work for any code embedded in `<pre>` or `<code>` tags. This was created to hopefully speed up posting code into environments where support for scripting is unknown or very limited.

You can pipe the output of markdown-generated html::

  > multimarkdown example1.md | colorize-html > example1.html


Styles
------

Use one of the styles that comes with pygments::

  > mmd example1.md | colorize-html -s monokai > example1.html

To see a list of styles use the `--list_styles` option.


Lexers
------

Valid lexers are all lexers available with Pygments. To see a list of these lexers view the Lexers.txt file, or type `--list_lexers` option::

  > colorize-html --list_lexers

If you are using this with markdown, you will want to use one of the lexer names as the name of your code section. For example::

  ```csharp
  var x = new object();
  ```

In this example `csharp` is one of the supported lexers, which you can check by querying it with the `--find_lexer`.::

  > colorize-html --find_lexer cshar
  Lexer not found.
  > colorize-html --find_lexer csharp
  C# :: [csharp, c#]


Other
-----

Sometimes it's useful to use a language as a default, which makes it easier for `colorizer` to identify code blocks in the html. This works really well on html source that was not created with markdown::

  > colorizer -f example1.html -d csharp -o example1-hl.html

If you publish posts on blogs that don't allow inserting your own styles or scripts (i.e. SharePoint), you can use the `-i` option::

  > cat example1.html | colorizer-html > example1-hl.html


Usage
------

For a full list of options use `-h`

::
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
