# This is not a blog

## Lesser known refactorings

* Convert comment to function name.
* Convert unit test to assertion.
* Convert assertion to type error.

## Thu Feb 25 18:09:48 MSK 2016

Parsing is considered a solved problem. Unfortunately, this view is naïve, rooted in the widely believed myth that programming languages exist.
http://cacm.acm.org/magazines/2010/2/69354-a-few-billion-lines-of-code-later/fulltext

## Mon Feb 15 00:22:27 MSK 2016

Errors lead to failures https://www.usenix.org/system/files/conference/osdi14/osdi14-paper-yuan.pdf


## Thu Jan 28 11:45:45 MSK 2016

It dawned on me that

1. GCC is implemented in C++
2. Clang is implemented in C++
3. HotSpot is implemented in C++
4. Python is implemented in C
5. Ruby is implemeted in C
6. V8 is implemented in C++
7. PHP is implemented in C

I don't know what language is .NET implemented in, but I guess that significant
part of it is C++.

I hope Rust will change it in several decades =)

## Mon Jan 11 17:43:03 MSK 2016

I think one of the most compelling features of Emacs is its universal text
user interface. And one of the main features of the interface is the absense of
modal dialogs. Seriously, modal dialogs kill the flow, because their placement
is totally unpredictable.


## Fri Jan  8 00:52:59 MSK 2016

I've just realized that to become a daemon, one should kill one's father and
grandfather. Makes perfect sense :)


## Sun Jan  3 04:17:56 MSK 2016

Having spend two weaks debugging a strange TCP performance degradation and
discovering Nagle's algorithms at the end, I can't recommend this strongly
enough: http://gafferongames.com/networking-for-game-programmers/. I wish I've
read it two months ago (or when I first stumbled upon a Go series couple of
years ago) :)


## Fri Dec 25 02:03:28 MSK 2015

A bad photo of an exceptional data visualisation: https://imgur.com/usWXmhM

A. k. a latency numbers every programmer must know.

## Sat Dec 12 17:20:11 MSK 2015

The amount of work I do is absolutely independent of the amount of time I
allocate for it.


## Fri Dec 11 17:44:11 MSK 2015

http://www.staff.science.uu.nl/~gadda001/goodtheorist/

## Sat Nov 21 05:34:47 MSK 2015

Late night compiler errors: There is no `mio` in `mio`.

## Wed Nov  4 17:03:50 MSK 2015

This is really close to what I think about programming languages
http://bruceeckel.github.io/2015/08/29/what-i-do/

## Sun Nov  1 02:45:04 MSK 2015

[Glium](https://github.com/tomaka/glium) is an awesome Rust OpenGL library. It
has a nice [tutorial](http://tomaka.github.io/glium/book/) (wip) but
unfortunately it does not yet include a section on using linear algebra
libraries such as [cgmath](https://github.com/bjz/cgmath-rs) or
[nalgebra](https://github.com/sebcrozet/nalgebra).


I've spent quite some time trying to figure out how to use nalgebra with glium,
and I don't want you to do the same. So here is a small [example](https://github.com/matklad/bunny).


## Thu Oct 29 22:26:14 MSK 2015

Achievement unlocked, I am officially a contributor to Rust 1.4 release:
http://blog.rust-lang.org/2015/10/29/Rust-1.4.html :)

Rust is awesome. Rust community is awesome.


## Thu Oct 29 16:29:58 MSK 2015

Super duper Emacs plugin for Intellij IDEA:
https://plugins.jetbrains.com/plugin/7906

It fixes window switching (C-g, C-x 1, C-x 0 work as expected), fixes navigation
in tree menus (project structure), makes Switcher (C-x b) absolutely awesome and
adds a ton of editing commands (M-c finally!).


Just don't forget to activate Emacs+ keymap after installation :)

Hooray!!

## Tue Oct 27 22:51:33 MSK 2015

Don't fear the --force push.

A clean git history with targeted small commits and meaningful commit messages
is a great help for understanding the code. You will be able to use `git blame`
as `show docs` shortcut.

However it is impossible to produce a nice history right away, you'll have to
use `git rebase -i` or over history rewriting mechanisms. But with history
rewriting you won't be able to publish your work without `--force` ...

One way out of the trap is to use local branches and never `push` your work
until you are satisfied with the history. There are huge drawbacks with this
approach:

  * you changes are stored only on local computer,
  * your teammates don't know what you are doing,
  * you **will** change your mind about a good history after the push.


The alternative of using `git push --force`, while scary for the beginners, is
much better in my opinion. Here are a few tips about the `force`:

  * `force` cannot destroy information. All the commits are still on server, so
    even if you have done something wrong, it is readily revertable.

  * Don't use `--force`, use `--force-with-lease`. It will make sure that you
    are not accidentally dropping others work.

  * Force push only the branches you own. That is, don't force push to the
    master branch without the team announcement and agreement and, if your are
    using an old version of `git`, make sure you are pushing only the current
    branch (in the old days, git pushed all branches by default).


When using force push with pull requests remember that the comments to the
commits will be lost. So it is better to update PR only once, just before the
merge, or even to open a follow up PR with a nice history.


To recap:

  * Create your branch.
  * Write a ton of dirty commits, pushing them to the server ASAP so that your
    teammates know what you are working on and give early feedback.
  * Rewrite history with `git rebase -i`, push with `git push
    --force-with-lease` and make a PR.
  * Fix the PR.
  * Force push again.
  * Merge and rejoice.


And may the `--force-with-lease` be with you.


## Fri Oct 23 20:44:12 MSK 2015

One more TODO: http://blog.phil-opp.com/rust-os/2015/08/18/multiboot-kernel/


## Fri Oct 23 02:41:48 MSK 2015

The wu wei of programming: https://github.com/servo/servo/commit/8c301c291a210fb75b1b5c4eba928a146578e3e4


## Sat Oct 17 00:28:34 MSK 2015

Should definitely try this: https://littleosbook.github.io/

Reminded me a lot of http://nand2tetris.org/


## Thu Oct 15 18:54:51 MSK 2015

Just wow! https://github.com/alex/what-happens-when/blob/master/README.rst

## Tue Oct  6 22:18:52 MSK 2015

Git is awesome:
http://perl.plover.com/yak/git/
http://ftp.newartisans.com/pub/git.from.bottom.up.pdf


## Sat Sep 12 01:36:05 MSK 2015

Pure evil:

```python
def eval(expr, var):
    lam = lambda arg, body: lambda val: eval(
        body, lambda x: val if x == arg else var(x))
    app = lambda f, arg: eval(f, var)(eval(arg, var))
    return locals()[expr['type']](*expr['children'])

print(eval({'type': 'app',
            'children': [
                {'type': 'lam',
                 'children': ['x', {'type': 'var', 'children': ['x']}]},
                {'type': 'var',
                 'children': ['y']}]},
           {'y': 92}.get))

```

## Fri Sep  4 16:07:09 MSK 2015

Parsing is still a hard task:
http://tratt.net/laurie/blog/entries/parsing_the_solved_problem_that_isnt


## Thu Aug 20 10:53:44 MSK 2015

A real paper about servo's experience with Rust
http://arxiv.org/pdf/1505.07383.pdf


##Tue Aug 18 10:48:43 MSK 2015

A good intro talk about the Rust programming language, with brilliant Q&A
section: https://www.youtube.com/watch?v=d1uraoHM8Gg

But two things are missing:
  * Ergonomics, usability and quality of implementation of the language. They
    are really high with rust (for example, a story about stability:
    http://blog.rust-lang.org/2014/10/30/Stability.html)
  * It's really hard to grasp the rust ownership model from the slides, because it
    is not what is found in mainstream languages (although C++11 with move
    semantics goes in this direction). You'll have to write some code to
    appreciate the borrow checker =)


##Sat Aug 15 00:06:43 MSK 2015

A really nice talk by Crockford: https://www.youtube.com/watch?v=bo36MrBfTk4#t=1135


##Thu Aug 13 13:17:42 MSK 2015

Found knowledge: always prefer `git push --force-with-lease` to  `git push
--force`. Nice [explanation](https://developer.atlassian.com/blog/2015/04/force-with-lease/).

Thank you, Magit!


##Tue Aug 11 00:49:03 MSK 2015

An awesome collection of small visual game related algorithms:
[http://www.redblobgames.com/](http://www.redblobgames.com/).

The [hexgrid](http://www.redblobgames.com/grids/hexagons/) post was really helpful
for this year's [icpf contest](https://github.com/lambda-llama/icfpc2015).


##Mon Aug  3 22:59:42 MSK 2015

A nice DB talk: [http://www.youtube.com/watch?t=10&v=fU9hR3kiOK0](http://www.youtube.com/watch?t=10&v=fU9hR3kiOK0)
