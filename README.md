# vanilla-js-crud

A single browser page for a short list of people and ice cream flavors. You type a name and a flavor, then add, edit, or delete rows. The list stays in memory on the page. Reloading the page clears it.

The page is `index.html`. It has no server, no database, and no packages.

## Prerequisites

- A web browser.
- Python 3, if you use the local server command below. Opening `index.html` directly does not need Python.

## Install, build, run, and test

There is nothing to install and nothing to build. The repository has no test script.

From the repository root, serve the page:

```bash
python3 -m http.server 8080
```

Open [http://127.0.0.1:8080/](http://127.0.0.1:8080/). The server prints logs in that terminal. Stop it with Ctrl+C.

You can also open `index.html` in a browser without a server. The script runs in the page either way.

## Usage

1. Enter a full name and an ice cream flavor. Both fields are required. If you submit with one empty, the page shows "Please fill out all fields."
2. Submit adds a row in the form `1) Name : Flavor`, with Edit and Delete buttons. The form fields are cleared after submit.
3. A new flavor is rejected when it equals an existing flavor, or when it matches an existing flavor as a case-insensitive regular expression. The page then shows the alert "No duplicate ice cream flavors" and does not add a row. For example, `van` matches `Vanilla`. A flavor that is not a valid regular expression, such as `(`, throws in the browser and is not added.
4. Edit fills the edit form with that row. Save updates the name and flavor when both fields are non-empty, then hides the edit form. If either field is empty, the page shows the alert "No blank inputs or duplicate Ice Cream names. No edits made." and leaves the row as it was. Save does not check for a duplicate flavor.
5. Delete removes that row and redraws the list.

## Layout

```text
index.html    page markup and the script that updates the list
README.md     this file
```

## License

This repository does not include a license file.
