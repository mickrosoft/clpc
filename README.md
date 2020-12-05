Common Lisp Programming Challenge
=================================

Learn Common Lisp (CL) together with a community of other learners and
experts.

If you are a beginner to CL, this challenge will help you to get started
with setting up a development environment from scratch and begin the
journey of learning CL together with other community members. If you are
an expert at CL, you are welcome to hang out with us in our
[forums](#forums) and help others with their questions.

This repository provides some setup exercises and code examples that
participants of this challenge can work through for every week of the
challenge.

Each week's exercise is composed of 5 units. Each unit is intended
to take roughly 1 hour of work. Therefore each week may involve about 5
hours of work. Hopefully, this will allow people with busy schedules to
participate in this challenge too.

The content of this repository is available under the [CC BY 4.0][CCBY]
license.


Contents
--------

* [Week 1](#week-1)
  * [Unit 1: SBCL](#unit-1-sbcl)
    * [Unit 1.1: Basics](#unit-11-basics)
    * [Unit 1.2: Install SBCL](#unit-12-install-sbcl)
  * [Unit 2: Emacs](#unit-2-emacs)
    * [Unit 2.1: Install Emacs](#unit-21-install-emacs)
    * [Unit 2.2: Emacs Init File](#unit-22-emacs-init-file)
    * [Unit 2.3: Emacs Help](#unit-23-emacs-help)
  * [Unit 3: SLIME](#unit-3-slime)
    * [Unit 3.1: Install SLIME Using MELPA](#unit-21-install-slime-using-melpa)
    * [Unit 3.2: Install SLIME Using Git](#unit-21-install-slime-using-git)
    * [Unit 3.3: Use SLIME](#use-slime)


Week 1
------

## Unit 1: SBCL

> "Lisp is worth learning for the profound enlightenment experience you
> will have when you finally get it. That experience will make you a
> better programmer for the rest of your days, even if you never
> actually use Lisp itself a lot." -- Eric S. Raymond

This unit shows how to quickly setup SBCL on your system.


### Unit 1.1: Basics

First, a couple of basics:

 1. Lisp is not a single programming language. It is a family of
    programming languages with a distinctive fully parenthesized prefix
    notation. Some popular dialects of Lisp are Common Lisp, Scheme,
    Clojure, Emacs Lisp, Racket, etc.

 2. Common Lisp is a dialect of Lisp with an ANSI standard. There are
    many implementations of Common Lisp in the form of compilers as well
    as interpreters. Some examples are Steel Bank Common Lisp (SBCL),
    Clozure CL (CCL), CLISP, etc. Clozure CL should not be confused with
    Clojure. Clozure CL is a compiler implementation for Common Lisp
    whereas Clojure is a separate dialect Lisp meant for the Java
    platform.

In this document, we work with Common Lisp only. Take a look at
https://common-lisp.net/implementations for a list of some of the
popular ones. We choose SBCL for this unit because it is the most
popular free and open source implementation of Common Lisp. It is also
known for its good performance.


### Unit 1.2: Install SBCL

Perform the following steps to get started with SBCL:

 1. Install SBCL.

    On macOS, it can be easily installed with Homebrew with the
    following command:

    ```sh
    brew install sbcl
    ```

    On Debian, Ubuntu, or any Debian/Ubuntu-based GNU/Linux system, it
    can be installed with the following command:

    ```sh
    apt-get install sbcl
    ```

    See http://www.sbcl.org/platform-table.html for download and
    installation details for other operating systems.

 2. Open your favorite editor, type this code, and save it as hello.lisp:

    ```lisp
    (format t "hello, world~%")
    ```

    Now enter this command to run the program:

    ```sh
    sbcl --script hello.lisp
    ```

 3. Congratulations! You have a working Common Lisp program now. Take a
    moment and [share your success on Twitter](https://twitter.com/compose/tweet?text=I+just+began+my+%23CommonLispProgrammingChallenge+with+a+%22hello%2C+world%22+program%3A%0A%0A(format+t+%22hello%2C+world~%25%22)%0A%0AJoin+this+challenge+with+%40spxycc+and+me.+Let+us+spread+the+joy+of+learning+this+beautiful+programming+language.+See+https%3A%2F%2Fspxy.org%2Fcc%2Fclcc%2F+and+learn+how.)!

 4. Open [Practical Common Lisp](http://www.gigamonkeys.com/book/)
    written by Peter Seibel and start working through the book. Get some
    head start with this book if you can afford the time right now. We
    will return to this book after going through a couple of more
    units to set up the development environment.

 5. Also, join us at our community forums, share your progress, as well
    as help and encourage others who are also participating in this
    programming challenge. Here are our community forum details:

      - Reddit: [r/spxy](https://www.reddit.com/r/spxy/)
      - Matrix: [#spxy:matrix.org](https://app.element.io/#/room/#spxy:matrix.org)
      - Freenode: [#spxy](https://webchat.freenode.net/#spxy)
      - Twitter: [@spxycc](https://twitter.com/spxycc)
      - Mailing list: [groups.google.com/g/spxy](https://groups.google.com/g/spxy)

    You don't have to join each one of them. Just one or two where you
    feel comfortable hanging out and share your updates, code examples,
    post links, discussion posts, questions, and answers there.

In the next few units, we will see how to set up an interactive
programming environment with Emacs and SLIME.


## Unit 2: Emacs

> "Calling EMACS an editor is like calling the Earth a hunk of dirt." --
> Chris DiBona

While it is perfectly possible to write Common Lisp programs and develop
complex Common Lisp projects with any editor or IDE that has good
support for Common Lisp, Emacs and SLIME is perhaps the most popular
development environment in the Lisp community. In this unit, we will
see how to set up GNU Emacs.


### Unit 2.1: Install Emacs

This unit is useful for those who have little to no Emacs experience.
If you are an experienced Emacs user, please proofread this unit and
if you find any issues, [create issues][ISSUES] or send us pull
requests. Perform the following steps to get started with Emacs:

 1. See https://www.gnu.org/software/emacs/download.html for Emacs
    download information. Here are some common commands:

    On macOS, enter the following command if you use Homebrew:

    ```
    brew cask install emacs
    ```

    On Debian, Ubuntu, etc., enter the following command if you use the
    system in terminal mode only (i.e., no GUI desktop):

    ```
    sudo apt-get install emacs
    ```

 2. Enter the following command to run Emacs:

    ```
    emacs
    ```

    On macOS, you may receive the following error message in a dialog
    box:

    ```
    “Emacs.app” can’t be opened because Apple cannot check it for
    malicious software.
    ```

    To resolve this issue, go to Apple menu > System Preferences >
    Security & Privacy > General and click `Open Anyway`.

 3. Within Emacs, enter the following command to open file, say,
    `~/hello.txt`:

    ```
    C-x C-f ~/hello.txt RET
    ```

    A new buffer to edit `~/hello.txt` is created. If a file with that
    name exists on your file system, then it loads the content of the
    file into the buffer.

    Note that in the Emacs world (and elsewhere too), we use the
    notation `C-` to denote we should press the <kbd>ctrl</kbd> and hold
    it while pressing the next key. For example, what is often denoted
    as <kbd>ctrl</kbd> + <kbd>x</kbd> is denoted as `C-x` here.

    Similarly, `RET` denotes the <kbd>enter</kbd>/<kbd>return</kbd> key.

    Another important thing to note is that when a command has two
    consecutive `C-` key sequences, you don't really have to press and
    hold the <kbd>ctrl</kbd> key twice. Instead, you can press and hold
    <kbd>ctrl</kbd> key once at the beginning, then press the two other
    keys, and then release the <kbd>ctrl</kbd> key. This shortcut is
    more convenient to work with. For example, for `C-x C-f`, you can
    press and hold <kbd>ctrl</kbd>, then press <kbd>x</kbd>, then press
    <kbd>f</kbd>, and then release <kbd>ctrl</kbd>. In other words,
    think of `C-x C-f` as `C-(x f)`.

 4. Now type some text into the buffer. Type out at least 3-4 words. We
    will need it for the next two steps.

 5. Move backward by one word with the following command:

    ```
    M-b
    ```

    The notation `M-` denotes pressing and holding the meta key. What's
    a meta key? It is usually the <kbd>option</kbd>/<kbd>alt</kbd> key
    on the keyboard. The <kbd>esc</kbd> key also works as the meta key
    but most people use the <kbd>alt</kbd> or <kbd>option</kbd> key as
    the meta key. In case, you are having trouble with getting the
    <kbd>alt</kbd>/<kbd>option</kbd> key working with Emacs, read [this
    article](https://www.emacswiki.org/emacs/MetaKeyProblems).

    Similarly, move forward by one word with the following:

    ```
    M-f
    ```

 6. The `C-g` key sequence cancels the current command. This can be used
    when you mistype a command and want to start over or if you type a
    command partially, then change your mind and then you want to cancel
    the partially typed command. Try out these examples:

    ```
    C-x C-f C-g
    ```

    ```
    C-x C-g
    ```

 7. Save the buffer to a file on the file system with this command:

    ```
    C-x C-s
    ```

 8. Quit Emacs:

    ```
    C-x C-c
    ```

Now you know how to start Emacs, open a file, save it, and quit. Improve
your Emacs knowledge further by taking the Emacs tutorial that comes
along with Emacs. First, start Emacs again and then enter the following
command to start the tutorial:

```
C-h t
```

The key-bindings to perform various operations like creating file,
saving file, quitting the editor, etc. may look arcane at first, but
repeated usage of the key-bindings develops muscle memory soon and after
having used them for a few days, one does not even have to think about
them. The fingers do what the mind wants effortlessly due to muscle
memory.

While you are getting used to the Emacs key-bindings,
keep this [GNU Emacs Reference
Card](https://www.gnu.org/software/emacs/refcards/pdf/refcard.pdf) handy
with you. Also, if you are using it in GUI mode, then the menu options
can be quite helpful. The menu options contain frequently used
operations. The option for each operation also displays the key-bindings
that can be used to invoke the same operation.


### Unit 2.2: Emacs Init File

Let us now see how to customize Emacs with an initialization file.
Perform the following steps:

 1. Run Emacs again with the following command in the shell:

    ```sh
    emacs
    ```

 2. In Emacs, enter this command to create a new file at
    `~/emacs.d/init.el`:

    ```
    C-x C-f ~/emacs.d/init.el RET
    ```

 3. Then add the following lines of Emacs Lisp code:

    ```elisp
    (load-theme 'wombat)
    (menu-bar-mode -1)
    (tool-bar-mode -1)
    (scroll-bar-mode -1)
    (setq inhibit-startup-screen t)
    ```

    The first line tells Emacs to load a beautiful dark color built-in
    theme known as `wombat`. If you want to check the other built-in
    themes, enter `M-x load-theme` and then press <kbd>tab</kbd> to see
    the available built-in themes.

    The next three lines remove the menu bar, tool bar, and the scroll
    bar from Emacs running in GUI mode. This makes the window look
    minimal.

    The last line inhibits the startup screen with the `Welcome to GNU
    Emacs` message.

    As a beginner to Emacs, you might want to only load a theme in your
    `~/emacs.d/init.el`. Don't disable the menu bar, tool bar, and
    scroll bar if you are not comfortable yet. Similarly, the startup
    screen useful information for beginners, so you might want to gain
    more experience with Emacs before disabling it.

 4. Quit Emacs now:

    ```
    C-x C-c
    ```

 5. Start Emacs again:

    ```sh
    emacs
    ```

    Emacs should now load with the theme and customization set in your
    `~/emacs.d/init.el`.

    Emacs supports a number of initialization files such as `~/.emacs`,
    `~/.emacs.el`, `~/.emacs.d/init.el`, etc. Traditionally, Emacs users
    kept their initialization program in `~/.emacs`. However, it may be
    more convenient to have all your Emacs in one directory, i.e.,
    `~/.emacs.d`, so this section recommends keeping your initialization
    program in `~/.emacs.d/init.el`.


### Unit 2.3: Emacs Help

Emacs has a rich built-in help and beginners as well as experienced
users rely heavily on the built-in help. Here are some steps to get
started with the help system:

 1. Enter the following command to get help on how to use the help
    features:

    ```
    C-h C-h RET
    ```

 2. Enter the following command to search for commands whose name match
    the given `PATTERN`:

    ```
    C-h a PATTERN RET
    ```

    Note that `PATTERN` here is a placeholder for the actual pattern you
    want to search. Here is a concrete example that searches for
    commands with `buffer` in their names:

    ```
    C-h a buffer RET
    ```

 3. Enter the following command to get help for a key sequence:

    ```
    C-h k KEY-SEQUENCE
    ```

    Note that `KEY-SEQUENCE` here is a placeholder for the actual key
    sequence. Here are a few concrete examples:

    ```
    C-h k C-x C-f
    ```

    ```
    C-h k C-g
    ```

 4. Enter the following command to get help for a specific symbol.

    ```
    C-h o SYMBOL RET
    ```

    Note that `SYMBOL` here is a placeholder for the actual symbol. Here
    are a few concrete examples:

    ```
    C-h o load-theme RET
    ```

    ```
    C-h o menu-bar-mode RET
    ```


## Unit 3: SLIME

SLIME stands for Superior Lisp Interaction Mode for Emacs. It is an
Emacs mode that adds support for interacting with a running Common Lisp
process for compilation, debugging, document lookup, etc. while
developing Common Lisp applications.

There are two popular ways to install SLIME. The easiest way is to
install from MELPA. Another way is to install SLIME is from its Git
repository. Both ways are presented below. If you are confused which way
to choose, just install SLIME from MELPA and skip the section about
installing from Git.


### Unit 3.1: Install SLIME Using MELPA

MELPA stands for Milkypostman's Emacs Lisp Package Archive. It is as a
repository of Emacs packages. GNU Emacs version 24 and later uses Emacs
Lisp Package Archive (ELPA) but not MELPA as the default repository for
packages. Since, SLIME is available in MELPA but not in ELPA, we
configure Emacs to use MELPA and then install SLIME from it.

Perform the following steps to install SLIME from MELPA:

 1. Start Emacs with this command:

    ```sh
    emacs
    ```

 2. Edit `~/.emacs.d/init.el` with this command:

    ```
    C-x C-f ~/.emacs.d/init.el RET
    ```

 3. Add the following Emacs Lisp code to the initialization file:

    ```elisp
    (require 'package)
    (add-to-list 'package-archives '("melpa" . "https://melpa.org/packages/") t)
    (package-initialize)
    (setq inferior-lisp-program "sbcl")
    ```

    The first three lines initializes Emacs to use Milkypostman's Emacs
    Lisp Package Archive (MELPA) as a package repository. GNU Emacs
    version 24 and later use Emacs Lisp Package Archive (ELPA) but not
    MELPA as the default repository for packages. Since, SLIME is
    available in MELPA but not in ELPA, we configure Emacs to use MELPA.

    The last line pre-emptively sets the Lisp program to be used by
    SLIME to SBCL.

 4. Save the Emacs initialization file:

    ```
    C-x C-s
    ```

 5. Reload the Emacs initialization file:

    ```
    M-x load-file RET ~/.emacs.d/init.el RET
    ```

 6. Download the list of packages available in ELPA and MELPA.

    ```
    M-x package-refresh-contents RET
    ```

 7. Install SLIME:

    ```
    M-x package-install RET slime RET
    ```

 8. Launch SLIME:

    ```
    M-x slime
    ```

    A new buffer named `*slime-repl sbcl*` should appear with the
    following prompt:

    ```
    CL-USER>
    ```

    This is a Read-Eval-Print-Loop (REPL) where you can evaluate Common
    Lisp expressions.


### Unit 3.2: Install SLIME Using Git

This is an alternate way to install SLIME. In this section, we see how
to install SLIME from its Git repository. If you have already installed
SLIME from MELPA using the steps in the previous section, you may skip
this section entirely and go straight to the next section.

Here are the steps to install SLIME from its Git repository:

 1. Clone the Git repository of SLIME. In the following command, we
    clone it to the home directory but you may clone it to any directory
    you are comfortable with:

    ```sh
    cd ~
    git clone https://github.com/slime/slime.git
    ```

 2. This is an optional step. Byte-compile SLIME with the following
    command:

    ```sh
    cd slime
    make compile contrib-compile
    ```

    This step is done only for improved performance. SLIME works fine
    even if you skip this step. That's why this is an optional step.

 4. Start Emacs with this command:

    ```sh
    emacs
    ```

 5. Add the following Emacs Lisp code to the initialization file:

    ```elisp
    (add-to-list 'load-path "~/slime")
    (require 'slime-autoloads)
    (setq inferior-lisp-program "sbcl")
    ```

    If you cloned to the Git repository of SLIME to a location other
    than your home directory, update the first line of this Emacs Lisp
    code accordingly.

 6. Save the Emacs initialization file:

    ```
    C-x C-s
    ```

 7. Reload the Emacs initialization file:

    ```
    M-x load-file RET ~/.emacs.d/init.el RET
    ```

 8. Launch SLIME:

    ```
    M-x slime
    ```

    A new buffer named `*slime-repl sbcl*` should appear with the
    following prompt:

    ```
    CL-USER>
    ```

    This is a Read-Eval-Print-Loop (REPL) where you can evaluate Common
    Lisp expressions.


### Unit 3.3: Use SLIME

 1. Enter this in the REPL:

    ```lisp
    (+ 1 2)
    ```

    The following result should appear when you press <kbd>enter</kbd>:

    ```
    3
    ```

 2. Try one more example in the REPL:

    ```lisp
    (format t "hello, world~%")
    ```

    The following result shoud appear on pressing <kbd>enter</kbd>:

    ```
    hello, world
    NIL
    ```


License
-------

The content of this repository is licensed under the
[Creative Commons Attribution 4.0 International License][CCBY].

You are free to share the material in any medium or format and/or adapt
the material for any purpose, even commercially, under the terms of the
Creative Commons Attribution 4.0 International (CC BY 4.0) License.

This document is provided **as-is and as-available,**
**without representations or warranties of any kind,** whether
express, implied, statutory, or other. See the
[CC BY 4.0 Legal Code][CCBYLC] for details.

[CCBY]: http://creativecommons.org/licenses/by/4.0/
[CCBYLC]: https://creativecommons.org/licenses/by/4.0/legalcode
[ISSUES]: https://github.com/spxy/clpc/issues