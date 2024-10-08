# scratchapi-python

[![PyPI - Version](https://img.shields.io/pypi/v/scratchapi-python)](https://pypi.org/project/scratchapi-python/)
[![GitHub Release](https://img.shields.io/github/v/release/Artcas2/scratchapi-python)](https://github.com/Artcas2/scratchapi-python/releases/latest)
[![GitHub License](https://img.shields.io/github/license/Artcas2/scratchapi-python)](https://github.com/Artcas2/scratchapi-python/blob/main/LICENSE)

A scratch API wrapper for Python, created by [Artcas2](https://scratch.mit.edu/users/Artcas2/).

## Installation

To install the library, run the following command:
```console
pip install -U scratchapi-python
```

## Example

```python
import scratchapi

session = scratchapi.login("username", "password")

user = session.get_current_user()
print("Follower count:", user.get_follower_count())
print("Following count:", user.get_following_count())
print("Project count:", user.get_project_count())

followers = user.get_followers(limit=1)
print("\nLast follower:")
for follower in followers:
    print(follower)

project = scratchapi.get_project("731849091")
print(f"\nProject stats: {project.loves} loves and {project.favorites} favs.")
```

## Usage

#### Logging in with username and password

```python
import scratchapi

session = scratchapi.login("username", "password")
```

#### Logging in with a session id

```python
import scratchapi

session = scratchapi.Session("username", "session_id")
```

#### Session attributes

```
session.username
session.session_id
session.email
session.xtoken
session.new_scratcher
session.banned
```
