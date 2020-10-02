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

## Mention the getting-started in your README

A good readme contains a succinct section to help people get started
contributing to the code. Here’s what I had written for that particular
project:

```markdown

## Contribute

1. Clone the repository.
1. Install [Poetry].
   This tool serves similar functionality as Pipenv. As it is usable across
   projects, it is advisable to [install in to your user directory, regardless
   of virtual environments][poetry-installation].
1. Install the development dependencies using `poetry`:

   ```bash
   poetry install
   ```

   This will automatically install the development dependencies, as well as the
   current project, inside of a virtual environment, managed by poetry.

1. With your virtual environment activated, run `pre-commit install`. This will
   ensure you run the git hooks that are configured in this repo (see
   [pre-commit-config.yaml](./.pre-commit-config.yaml)). The first time you run
   this, it will be slow, as all external tools will need to get downloaded and
   get their own virtual environments. Any subsequent call is fast.
   It’s recommended to try running the hooks against all the files:
   `pre-commit run --all-files`.

   Note: one of the hooks checks the format of your commit messages. To make
   better use of the git log, a format is imposed, so that we may avoid
   senseless commits like "fix", which give very little info and thus make it
   harder to trace changes. To simplfy adherence to the commit message format,
   the tool [commitizen] is installed. Rather than issuing `git commit`, run
   `cz commit` and it will walk you through the commit procedure to generate
   more useful commit messages.

[poetry]: https://python-poetry.org/
[poetry-installation]: https://python-poetry.org/docs/#installation
[commitizen]: https://commitizen-tools.github.io/commitizen/

```

[pre-commit]: https://pre-commit.com/
