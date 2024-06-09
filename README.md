# today.nb

Open or create a day's note.

A plugin for `nb` <https://github.com/xwmx/nb>.

Author: Jangari <https://github.com/jangari>.

## Installation

```
nb plugin install https://github.com/jangari/today.nb/blob/main/today.nb-plugin
```

## Usage

`nb today [<offset>] [--no-open | --path | --date <datestr>]`

## Description

Create, open, or return the paths for notes based on dates, such as today by default, or with an offset, a number of days before of after today, or for specific dates expressed by a string.

## Arguments
| Argument | Description |
| --- | --- |
| `[<offset>]` | Specifies the offset from the current date. If provided, the note will be created for the date that is <offset> days away from the current date. Use negative numbers for dates in the past and positive numbers for future dates. For example, -1 represents yesterday, +1 represents tomorrow, -2 represents two days ago, and so on. If not provided, the note will be created for the current date.|

## Options

| Option | Description |
| --- | --- |
| `-n`, `--no-open`              | Do not open after creating.|
| `-p`, `--path`, `--paths`        | Return the note path instead of opening. Useful for integration with external editors. Implies `--no-open`.|
| `-d`, `--date <datestr>`       | Create/open note for date represented by <datestr>. Requires GNU date to be installed and its path provided in `NB_TODAY_DATE_CMD`. This option overrides any provided `<offset>`. See Examples section.|

## Environment Variables

| Variable | Description |
| --- | --- |
| `NB_TODAY_DATE_CMD`           |Specifies the path to the `date` command to use for date calculations. If not set, the script will use the system's default `date` command. On MacOS, the builtin `date` command does not support the `--date` option. GNU Date is recommended.|
| `NB_TODAY_FILENAME_PATTERN`   |Specifies the strftime pattern to use for generating the filename of today's note. If not set, the default pattern is '%Y-%m-%d', yielding note filenames such as '2024-05-01.md'.|
| `NB_TODAY_TITLE_PATTERN`      |Specifies the strftime pattern to use for generating the title of daily notes. If not set, the default pattern is '%Y-%m-%d'.|
| `NB_TODAY_FILE_PATH`          |Specifies the path relative to the notebook where daily notes should be saved. If not set, daily notes are saved to the notebooks' root.|

## Examples

| Example | Description |
| --- | --- |
|`today`|              Create or open today's note|
|`today -1`|           Create or open yesterday's note|
|`td -n +1`|           Create tomorrow's note without opening it|
|`today -2 -p`|        (Create and) Print the path for the note for two days ago|
|`today --no-open`|    Create today's note without opening it|
|`day -d "+3week"`|    Create a note for the day 3 weeks after today|
|`today -nd "June 20"`|Create a note for June 20 without opening it|
|`td -pd "last year"`| (Create and) Print the path for the note for one year ago|
|`sample:today +1`|    Create tomorrow's note in the `sample` notebook|

## See Also

`man 3 strftime`
`gdate`

## Aliases

`nb day`
`nb td`
