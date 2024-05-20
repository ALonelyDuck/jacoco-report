# jacoco-report

This is a forked GitHub action that I've modified for a personal project. It publishes the JaCoCo report as a comment in the Pull Request, providing customizable pass percentages for modified modules, files, and the overall project. A new feature I've added is the ability to view the coverage of just the changed files in your pull request, as well as an additional output parameter.

For the orignal project go to [Madrapps/jacoco-report](https://github.com/Madrapps/jacoco-report)

## Usage

### Inputs

- `paths` - [**required**] Comma separated paths of the generated jacoco xml files (supports wildcard glob pattern)
- `token` - [**required**] Github personal token to add commits to Pull Request
- `min-coverage-overall` - [*optional* {default: 80%}] The minimum code coverage that is required to pass for overall project
- `min-coverage-changed-files` - [*optional* {default: 80%}] The minimum code coverage that is required to pass for changed files
- `update-comment` - [*optional* {default: false}] If true, updates the previous coverage report comment instead of creating new one.
  Requires `title` to work properly
- `title` - [*optional*] Title for the Pull Request comment
- `skip-if-no-changes` - [*optional* {default: false}] If true, comment won't be added if there is no coverage information present for
  the files changed
- `pass-emoji` - [*optional* {default: :green_apple:}] Emoji to use for pass status shown when 'coverage >= min coverage' (should be a Github supported emoji).
- `fail-emoji` - [*optional* {default: :x:}] Emoji to use for fail status shown when 'coverage < min coverage' (should be a Github supported emoji).
- `continue-on-error` - [*optional* {default: true}] If true, then do not fail the action on error, but log a warning
- `debug-mode` - [*optional* {default: false}] If true, run the action in debug mode and get debug logs printed in console

### Outputs

- `coverage-overall` - The overall coverage of the project
- `coverage-changed-files` - The total coverage of all changed files
- `coverage-changed-percentage` - The percentage of coverage change in the modified files.

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
