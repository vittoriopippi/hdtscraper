# HDTscraper
This module allows you to easily scrape the information of movies and TV series uploaded to the [HDtorrents](http://hdtorrents.xyz/) website.

## Installation

To install the module just run the following code:
```
pip install hdtscraper
```
# API
### Table of Contents

- [**hdtscraper**](#hdtscraper)
- [hdtscraper.**is_up**](#hdtscraper.is_up)
- [hdtscraper.**login**](#hdtscraper.login)
- [hdtscraper.**get_last**](#hdtscraper.get_last)
- [hdtscraper.**get_new**](#hdtscraper.get_new)
- [hdtscraper.**get_page**](#hdtscraper.get_page)
- [hdtscraper.**download_torrent**](#hdtscraper.download_torrent)

All your files and folders are presented as a tree in the file explorer. You can switch from one to another by clicking a file in the tree.

<a name="hdtscraper"/>

## hdtscraper(username, password)
[\[source\]](https://github.com/vittoriopippi/hdtscraper/blob/main/hdtscraper/main.py#L56)

- `username`: string containing the account username
- `password`: string containing the account password

Returns the `hdtscraper` object.

<a name="hdtscraper.is_up"/>

## hdtscraper.is_up(home_url='https://hdtorrents.xyz')
[\[source\]](https://github.com/vittoriopippi/hdtscraper/blob/main/hdtscraper/main.py#L15)


This is a static method used to assert that the website is up.

- `home_url`: url on which the check is performed

Returns `True` if the website is up, `False` otherwise.

<a name="hdtscraper.login"/>

## hdtscraper.login(self)
[\[source\]](https://github.com/vittoriopippi/hdtscraper/blob/main/hdtscraper/main.py#L43)

This function is automatically called before scraping the site. It only logs in if the last login was more than a certain amount of time ago. The length of the interval is defined by the `session_length` value present inside the `hdtscraper` class.

Returns the session after logging in.

<a name="hdtscraper.get_last"/>

## hdtscraper.get_last(self, movie_count, max_pages=50)
[\[source\]](https://github.com/vittoriopippi/hdtscraper/blob/main/hdtscraper/main.py#L48)

- `movie_count`: number of torrents to return
- `max_pages`: number of pages that will be taken into account

Returns a list containing the latest `movie_count` torrents uploaded. 

<a name="hdtscraper.get_new"/>

## hdtscraper.get_new(self, hd_id, max_pages=50)
[\[source\]](https://github.com/vittoriopippi/hdtscraper/blob/main/hdtscraper/main.py#L56)


- `hd_id`: HDtorrent id of a torrent
- `max_pages`: number of pages that will be taken into account

Return all uploaded torrents after the specified one.

<a name="hdtscraper.get_page"/>

## hdtscraper.get_page(self, page_index)
[\[source\]](https://github.com/vittoriopippi/hdtscraper/blob/main/hdtscraper/main.py#L69)

- `page_index`: index of an HDtorrents page starting from 0

Returns all torrents on the given page.

<a name="hdtscraper.download_torrent"/>

## hdtscraper.download_torrent(self, movie, dst_path)
[\[source\]](https://github.com/vittoriopippi/hdtscraper/blob/main/hdtscraper/main.py#L94)

- `movie`: a torrent returned by one of the functions above
- `dst_path`: path where to save the torrent

Returns `None`.
