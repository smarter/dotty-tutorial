## Dotty Tutorial

- [Dotty Tutorial Talk](http://guillaume.martres.me/talks/dotty-tutorial/#/)

### Getting started

- Join the [Gitter channel](https://gitter.im/lampepfl/dotty) !
- Compile your first program with Dotty:
```scala
git clone https://github.com/lampepfl/dotty.git
cd dotty
./bin/dotc tests/pos/HelloWorld.scala
./bin/dotr HelloWorld
```
- Play with the REPL:
```scala
./bin/dotr
```
- Dotty is a standard sbt project, instead of using the `dotc` wrapper, you can run the compiler from sbt, this is a lot more convenient when hacking on Dotty itself:
```shell
sbt
> run tests/pos/HelloWorld.scala
```

### Compiling an sbt project with sbt

- First, get [dotty-example-project](https://github.com/smarter/dotty-example-project) up and running
- Once you got that working, follow the README instructions to try to adapt an existing sbt project to work with Dotty
  - There are no cross-compiling examples yet (PR welcome!). For now, just comment out `crossScalaVersions` if you use it
  - You may have to remove some options from your `scalacOptions` that dotty does not support
- Dotty has been tested on very few existing Scala projects so far, so it's likely that you'll encounter a bug or missing feature!
  - We welcome bug reports, here are a few tips:
    - Take a look at [existing issues](https://github.com/lampepfl/dotty/issues) to see if yours has already been reported. If you're not sure, report it!
    - If the compiler crashed with a stacktrace or you got an unexpected crash at runtime, please paste the stracktrace to https://gist.github.com/ and link it in your report
    - If possible, please try to create a minimized testcase that demonstrates the issue. Ideally this should be a single `.scala` file that we can run with `dotc`, but a link to an sbt project that reproduces the problem is already very useful.

### Contributing

- The [Workflow](https://github.com/lampepfl/dotty/wiki/Workflow) has some tips on working on the compiler

If you'd like to contribute but are not sure what to do:
- If you tried to compile a project and it didn't work, you can try fixing it yourself!
- Otherwise, have a look at our [issue tracker](https://github.com/lampepfl/dotty/issues), especially the issues marked [Low hanging fruit](https://github.com/lampepfl/dotty/issues/1396)
- Here are some random ideas of things that may interest you:
  - Colors:
    - our REPL has syntax highlighting but it's a bit buggy/limited, try to improve it!
    - our errors/warning messages are still black and white, we should catch up with gcc/clang !
  - Find some option from `scalac` that we don't support but could be useful, like `-Xfatal-warnings`
  
