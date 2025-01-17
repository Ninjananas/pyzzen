# Pyzzen
Pyzzen is a very simple and basic **Py**thon Qui**zz** **En**gine.
Its goal is to offer a simple, lightweight, and ephemeral online quizz platform.

## Dependencies
Pyzzen has been tested on Python versions 3.10 and above.

Pyzzen depends on the following Python packages:
- quart
- quart_babel
- pydantic
- toml (for Python < 3.11)

Additionally, Pyzzen uses (and ships with) the following external projects:
- Simple.css (https://simplecss.org/) MIT Licensed
- MathJax (for math formulas in quizzes) (https://www.mathjax.org/) Apache-2.0 Licensed

## Installation
### Manual
You can manually install Pyzzen's dependencies and run it manually from the sources like any Python module.

### Using pip and PyPI
`pip install pyzzen`

## Usage
### Launching
Launch Pyzzen like any other Python module with `python -m pyzzen` for example.

You can change the listening port (default 5000) and the admin password (default "CHANGE ME") using the --port and the --admin-pass options from the command line.

### Creating a quizz
- login to the administration panel at `http://localhost:5000/admin` (Change the URL if you deploy somewhere else)
- Select and upload a quizz file. No formal specification has been made, but the sample__quizz.toml file in Pyzzen's repository covers what Pyzzen can do in quizzes.
- Select the newly created quizz in the list, and give the URL to participants

### Running the quizz
The interface is quite straightforward, I might write a better guide in the future.

# FAQ
### Does Pyzzen asks its users to access resources elsewhere?
No. No CDN is used, no data is sent from the users to another party.

### Does Pyzzen stores data on disk?
No. Pyzzen is *Ephemeral*. It also means than when you restart Pyzzen, you get a clean slate and everything is gone.

### Is Pyzzen safe?
Reasonably yes. Although, the admin password is handled in plain text and few considerations has been made about cheating, and no authentication is made at all for the users. Users can, if savvy enough, make multiple accounts for example (by using separate browsers).

I would advise a teacher that wants to grade their students not to use Pyzzen.

### Can I use HTTPS with Pyzzen?
Yes, for example by using a reverse proxy. Don't forget to forward the websocket at `/ws_reload` correctly.

### What about i18n?
Pyzzen's interface is in English by default, and translations exist in French. Here is the documentation I use to update the translations: 

https://quart-babel.readthedocs.io/en/latest/how_to_guides/using_translations.html