# apibay CLI

A small Python command-line tool for searching apibay.org, viewing an entry's details and files, and generating a magnet link.

## Requirements

- Python 3.7 or newer
- Internet access to apibay.org

The script uses only Python's standard library; there are no packages to install.

## Usage

Run commands from this directory:

```sh
./apibay.py search "the last starfighter"
./apibay.py details 83808736
./apibay.py magnet 83808736
```

`search` also accepts unquoted terms, which are joined into one query:

```sh
./apibay.py search the last starfighter
```

## Output

Search results show the ID, size, seeders/leechers, date added, and name. ID, size, and seeder/leecher column widths are calculated from the current result set to align values with minimal padding. Sizes use KB, MB, or GB with two decimal places; dates use `DD/MM/YY` in the machine's local timezone.

`details` begins with the same summary layout, followed by the description and a tab-separated list of file names and sizes. `magnet` prints a magnet URI for the entry.

Search and details use terminal colors when writing to an interactive terminal. Colors are disabled when output is redirected or `NO_COLOR` is set. API-provided text is filtered for terminal escape sequences and control characters before display.
