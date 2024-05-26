# today.nb-plugin

Open or create a day's note.

A plugin for `nb` <https://github.com/xwmx/nb>.

Author: Jangari <https://github.com/jangari>.

## Installation

`nb plugin install https://github.com/jangari/today.nb-plugin/blob/main/today.nb-plugin`

## Usage

`nb today [<offset>] [--no-open|-n]`

## Description

Create today's note if it doesn't already exist, and opens it if it does.

If an offset is provided (e.g., -1 for yesterday, +1 for tomorrow), the note for the specified day is created or opened.

Use the --no-open or -n flag to create the note without opening it.

Note is created using `YYYY-MM-DD` as both filename and note title by default. Both patterns can be overridden by setting the `NB_TODAY_FILENAME_PATTERN` and `NB_TODAY_TITLE_PATTERN` environment variables in `~/.nbrc` to the desired `strftime` patterns.

## Examples

`nb today             # Create or open today's note`
`nb today -1          # Create or open yesterday's note`
`nb today -2          # Create or open the note for two days ago`
`nb today --no-open   # Create today's note without opening it`
`nb today +1 -n       # Create tomorrow's note without opening it`

## See Also

`man 3 strftime`

## Aliases

`nb day`
