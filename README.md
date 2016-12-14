LaTeX
====

Introduction
----

LaTeX is a programming language for beautiful typesetting.


Background and context
----

### History

In the 1970s, computer typography was still in its infancy.
Computer scientist Donald Knuth felt very dissatisfied with the quality of
mathematical publishing available at the time.
He created a programming language called _TeX_ (pronounced "tech") intended to
automatically typeset mathematical content,
with strong principles of beauty foremost in mind.

TeX was very good at positioning type on a page,
but not so good at keeping track of a document's overall structure.
To have chapters, sections, figures, tables of contents and references required non-trivial programming.

Thus, in the 1980s, another computer scientist called Leslie Lamport released a set of extensions to TeX.
With Lamport's TeX extensions, people could more easily work on the most common types of documents:
articles, reports, letters, slides and books.
The word _LaTeX_ is short for "Lamport's TeX".
LaTeX quickly spread amongst mathematicians, physicists and computer scientists.


### LaTeX today

Although the original focus of LaTeX was mathematical typesetting,
its adherence to aesthetic principles,
combined with the availability of free, open source, and cross-platform LaTeX software,
gave it broad appeal.
It now has extensions in every discipline,
and is used by linguists, poets, playwrights, authors, musicians, philosophers and lawyers,
in addition to the more traditional cast of physicists, mathematicians, statisticians, engineers and computer scientists.

Due to its robustness and flexibility,
it also integrates with a wide variety of other tools commonly
used by scientists, programmers and academics.
Together with _R_ for statistical analysis, version control tools like Git or DropBox,
and Unix command line tools used in servers and embedded environments,
LaTeX forms one component of a rich and timeless computational ecosystem.

Glossary
----

* **Typesetting:** The science and art of positioning type on a page in preparation for publishing.
* **Natural language:** Human communication.
  Inconsistent, changeable, and poetic.
  Heavily dependent on social, historical and cultural context and cues for meaning.
* **Source code:** A plain text document mixing natural language and formal commands.
  Human programmers spend most of their time working on source code.
  This includes LaTeX users.
* **Plain text:** An unformatted document with no hidden information.
  Associated in many peoples' minds with the `.txt` extension,
  which can be opened in plain text editors like Notepad.
  Regardless of the extension, if a document is readable in a text editor like Notepad then it is a plain text file.
  LaTeX source code is usually given the `.tex` extension instead of `.txt`.
* **Implementation:** When an abstract standard is converted into practical, working software.
  LaTeX itself is only a standard for describing documents.
  This standard is implemented as LaTeX _compilers_.
  We usually don't worry about the distinction,
  but it is a useful idea to keep it in the back of one's mind.
* **Compiler:** A program that reads source code (the _input_) and translates it into another form (the _output_).
  The output would usually be difficult for humans to create manually.
  For example, a LaTeX compiler takes LaTeX source and outputs beautiful PDFs.
  It would be too complicated for most people to write a beautiful PDF from scratch,
  so we create LaTeX source code and then let the LaTeX compiler do the hard work.

Examples
----

### Hello world!

It is possible to keep learning new things about LaTeX every time you use it,
for the rest of your life.
However, to get started, it is sufficient to write just four lines of source code:

~~~{.tex}
\documentclass{article}
\begin{document}
Hello world!
\end{document}
~~~

Everything else you need to know, you can look it up when you need it.

Now let's have a closer look at the above four lines.

Everything beginning with a backslash is a formal LaTeX command.
Notice that `Hello world!` is just natural language;
most of what you write in LaTeX will be natural language.

The curly brackets are used to group letters together.
For example, we want the `\documentclass` command to see the whole word "article",
not just the first letter, "a".

When you run a LaTeX compiler on this source code,
the output PDF will only show the words "Hello world!".
The compiler knows that some commands are not intended for reading by the audience.

Sometimes you want to leave a note to yourself or your collaborators.
It is possible to hide part of your source code from the compiler using a _comment_.
Using comments is quite common in all programming languages.
In LaTeX, anything which appears after a percent sign, "`%`",
will be treated as a comment.

~~~{.tex}
\documentclass{article} % Instead of "article", we could put something like "report", which will completely change the appearance of the final document.
% Everything before \begin{document} is called the preamble.
% The preamble is where you can add a wide variety of customisations.

% End of preamble.
\begin{document}

Hello world! % Even with all these comments, your audience will still see nothing more than "Hello world!" in the final PDF.

\end{document}
~~~

Later, it will be useful to know that the `\begin` and `\end` commands are used
a lot in LaTeX to fence _environments_.
Every LaTeX project has a _document_ environment, to tell LaTeX which part
of the project contains content intended for the audience.


### An epsilon of mathematics

Although LaTeX is no longer just for mathematics,
it would be remiss to exclude _all_ mathematics from an introduction to LaTeX.

In mathematics, the Greek letter _epsilon_ (ε),
is conventionally used to represent "a very small quantity".
Eccentric 20th Century mathematician Paul Erdös even used to refer to young children as "epsilons".

Thus, this subsection is called _An epsilon of mathematics_,
since we will only cover the bare minimum.

Since mathematics has specialised typesetting requirements,
we need to tell LaTeX when we're switching into _math mode_.

It is kind of like how humans have _weekday mode_,
when they are content to do whatever their supervisor tells them to do,
and _weekend mode_,
when it would be inappropriate for their supervisor to make demands of their time.

In LaTeX, entering mathematics is like going on a small holiday away from natural language.

In the 1970s, it was very expensive to typeset mathematical formulas,
so Donald Knuth chose the dollar sign (`$`) for switching to math mode,
to remind himself of the money involved.
In particular, a double dolar sign, `$$` (with no spaces in between),
is one way to enter math mode.
Another double dollar sign is used to finish math mode and go back to normal mode.
This is required; unfortunately no holiday can last forever.

Now we look at two examples.

~~~{.tex}
\documentclass{article}

\begin{document}
Hello world! Here is some mathematics:

$$ e^{i\pi} + 1 = 0. $$ % Euler's beautiful equation.

$$ \lim_{\epsilon\rightarrow 0}\epsilon = 0. $$ % An epsilon in mathematics.
\end{document}
~~~

The above source code compiles into the following document:

![math example](./figures/math-example.png)

In the first equation, there are two things to notice:
the hat symbol `^` and the command `\pi`.

In math mode, the hat symbol means "raise whatever comes next".
Usually, this means to superscript it.
Meanwhile, `\pi` means to insert the character _π_.
Since Greek letters are used so often in mathematics,
you can enter them in LaTeX by putting a backslash in front of their English name.

In the second equation, we need to use the command `\lim`,
since not only does this stand for a formal mathematical concept,
but also we can't use normal mode text while in math mode.
We also notice another Greek letter entered with `\epsilon`,
and a command to enter an arrow symbol.

Finally, the underscore character, `_`, is kind of the opposite of '^'.
It means _lower_ whatever comes next.
Usually it will turn whatever comes next into a subscript,
but when used with special commands like `\lim` it works a little differently,
as shown in the output.


### A vector for poetry

Having asserted that LaTeX is for people in any discipline,
it behoves us to consider an application from the humanities.
Let's see how LaTeX goes with poetry.

In fact, LaTeX has a built-in _verse_ environment, used like so:

~~~{.tex}
\documentclass{article}

\begin{document}
Hello world! Here is some poetry:

\begin{verse}
  ResBaz in Summer: \\
  Everyone busy sweating \\
  Over LaTeX code.
\end{verse}

\end{document}
~~~

Notice how it is fenced by the `\begin` and `\end` commands, just like the
document environment.

The double backslash is used to force a line break.
This is required because LaTeX will usually aim to just make everything look as beautiful as possible,
so it will usually ignore line breaks in the source code.
(In general, to tell LaTeX you want a new paragraph,
you need to leave an entire blank line,
not just start a new line.)

The built-in verse environment is not very sophisticated, though.
If you want to do non-trivial poetry, you should tell LaTeX to use one of the
available extensions that have been written by people in the worldwide LaTeX community.
These extensions are called _packages_ and we tell LaTeX about them in the
_preamble_, before entering the document environment:

~~~{.tex}
\documentclass{article}

\usepackage{verse}

\begin{document}
Hello world! Here is some poetry:

\begin{verse}
  ResBaz in Summer: \\
  Everyone busy sweating \\
  Over LaTeX code.
\end{verse}

\end{document}
~~~

There are thousands of packages available for LaTeX,
covering everything from drawing complicated diagrams to automatically
formatting all your references in your preferred bibliography style.
One day you might even learn how to create your own packages to share with other people!
Since LaTeX is free and open source,
it is powered by the creative efforts of people just like you.


Challenges
----


Plenary
----


Bibliography
----
