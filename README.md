# This is not a blog

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
