# precommit-example

There are a lot of tools out there that take away the burden of configuring
your IDE to run linter tools (e.g. autoformatting code, checking for adherence
to a style guide, making sure code has no syntax errors, …). Or for you to
remember all these little things that make your code just that tiny bit better. 

Developers do wisely to use such tools. Even better is when these tools can be
set up for the entire team so everyone benefits from them and they happen
_before_ your changes end up at the CI/CD system, or -gasp- in production.

At Data Minded, I gave a talk about [pre-commit], a tool that does just that.
It is configured through one config file, that you can commit to your code
repo, so everyone in the team has the same git hooks configured, which benefits
the team, as you can keep code review more focussed on the hard parts, the
parts that require creativity in code.

I upload this example, which is used in one of the code bases I’m involved
with, so my colleagues can get a jumping board. 🚀

[pre-commit]: https://pre-commit.com/
