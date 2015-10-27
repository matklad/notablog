# This is not a blog

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
    teammates know what your are working on and give early feedback.
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
