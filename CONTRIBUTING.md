# Contributing to inkjs

**⚠️ This document is a work in progress.**

We're very happy to hear that you want to contribute! 🎊

## Asking question / Reporting issues / Getting in touch

### I have a question

1. Check whether it has been asked before or not. You can either search through
   [issues].
2. If it hasn't been asked before, open an issue.

[issues]: https://github.com/y-lohse/inkjs/issues

### I encountered a bug

Open an issue or fix the bug yourself and submit a pull request!

### I think _inkjs_ would be better with feature X…

We usually don't accept new features in _inkjs_. The purpose of the project is
to provide an implementation of ink in JavaScript, compliant with the reference
implementation.

If you feel that ink is missing a feature, we recommend that you bring it up in
the [main repository] first, or alternatively, in the official [Discord server].

[main repository]: https://github.com/inkle/ink
[Discord server]: https://discord.gg/inkle

## Rules & Conventions when porting code from C# #

1. Do not port comments from the C# codebase, but do add `inkjs`-centric comment
   when it make sense. For example, it's important to document when `inkjs`
   display a slightly different behavior than the reference implementation.

_To be added._

### Style guide

_inkjs_ uses [Prettier] and [ESLint] to ensure code consistency. We recommend
that you run prettier either on save or before submitting your PR. Our CI lints
every PR submitted, so make sure your code passes validation. Two NPM tasks
can help you:

- `lint` runs the linter
- `lint:fix` fixes lint errors and warnings automatically

[Prettier]: https://prettier.io/
[ESLint]: https://eslint.org/

### Porting tests & writing new specs

**inkjs** contains two test suites. The first one contains inkjs-centric tests,
while the second one has been ported from the reference C# implementation.

Both test suites are ran twice, first against the TypeScript code
(transpiled on the fly) and then, a second time, against the distributable,
minified resulting JavaScript file.

- `test` runs the full test suite, both in TypeScript and JavaScript;
- `test:typescript` runs the TypeScript test suite;
- `test:javascript` runs the JavaScript test suite;
- `test:javascript:dist` runs the test suite against the modern distributable
                         JavaScript file.
- `test:javascript:legacy` runs the test suite against the legacy distributable
                           JavaScript file.
- `test:compileFiles` compiles the fixtures required by the test case (requires
                      inklecate to be available in `$PATH`)

`test:compileFiles` needs to be run again every time new tests are added or when
porting a new version of the runtime. The fixtures should always be compiled
with the latest version of inklecate.

#### Porting tests from the reference implementation

_To be added._

#### Writing new specs

_To be added._