# Collaboration

You're going to be creating a news site collaboratively using branching and
pull-requests. The repository has been configured to require pull-requests
before code can be pushed to the main branch, meaning that you must do your work
on another branch and then create a pull request PR, requesting that another
developer review/approve your changes before the changes can be merged into the
main branch.

## Installing Third-Party Packages

Before starting, we need to perform a few setup tasks so that we can use some
tools to make sure our code will pass the tests that will be run when we merge
it into the main branch.

We are going to install some third-party software that will run some checks to
make sure our code passes certain tests. This is a common process used in
development teams. The tests are run as part of the PR process and if the test
fail the merge request will fail.

When a project uses third-party software, you need to use a package manager to
retrieve and maintain the connection to that software. The package manager that
we will use is npm (node package manager). It maintains a registry of the
packages that it has retrieved in the file named `packages.json` in the root of
the project folder and stores the packages in a folder called `node_modules`,
also in the root of the project folder.

The files in the node_modules folder are not included in the project's git
repository. They are added to the .gitignore file to prevent them from being
included when you do a commit. This is because you have the packages.json
registry that maintains the list of packages, and you can just issue the command
`npm install` within your project and all of the packages will be retrieved.

1. [Install node](https://nodejs.org/en/download/)
2. Run the following command: `npm install`.

## Code Quality Checks

The following tools can now be run to check whether our code has any of the
following issues:

- `npm run format`: Makes sure all the code in this repository is well-formatted
  (looks good).
- `npm run lint:md`: Will lint all of the Markdown files in this repository.
- `npm run lint:css`: Will lint all of the CSS files in this repository.
- `npm run validate:html -- ./path/to/file.html`: Validates all HTML files in
  the path provided.
- `npm run spell-check`: Goes through all the files in this repository looking
  for words it doesn't recognize. Just because it says something is a mistake
  doesn't mean it is! It doesn't know every word in the world. You can add new
  correct words to the [./.cspell.json](./.cspell.json) file so they won't cause
  an error.
- `npm run accessibility -- ./path/to/file.html`: Runs an accessibility analysis
  on all HTML files in the given path and writes the report to
  `/accessibility_report`

## Continuous Integration (CI)

For now you can think of Continuous Integration as a fancy way to say
"automatically check your code before you merge". Your project repositories will
all have CI scripts to help maintain a quality and consistent code base.

For this repo, when you open a PR to `main` in your repository, GitHub will
automatically do a linting check on the code in this repository, you can see
this in the[./.github/workflows/lint.yml](./.github/workflows/lint.yml) file.

If the linting fails, you will not be able to merge the PR. You can double check
that your code will pass before pushing by running any of the tests listed above
locally.

## Site Creation

### Requirements

- you must have an issue in GitHub for each task you are going to work on.
- you must create a new branch for each issue you work on.
- when you have completed the work for the issue, and are ready to merge it into
  the main branch, push your changes to GitHub, and then create a pull request
  and assign someone else to review/approve your changes.

### Step 1 - Create a markdown file for each team member.

There is a file named `team.md` that should contain a link to a markdown file
for each team member. I have included `anne.md` as an example.

### Step 2 - Create the news site, following the directions in [SPEC.md](SPEC.md).
