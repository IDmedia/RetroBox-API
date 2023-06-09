<div align="center">
  <img src="retrobox.svg" height="220px" width="auto" alt="RetroBox">
</div>

# Overview
RetroBox API streamlines your retro gaming experience by offering a powerful backend that organizes your roms and associated data. Simply import game lists using a DAT file, and let the API post-process your rom collection to automatically sort, verify, and scrape it. You can even assign emulators to platforms or games, so all your information is stored centrally.
This centralized storage enables future front-ends to easily integrate and search for games. You can request a specific game or all games for a given platform without any hassle. With all roms, media, and emulator files provided by the API, front-ends can offer a seamless one-click play experience, eliminating the need to mess with settings before enjoying your favorite game.

TL;DR:
While RetroBox API shares similarities with other **arr software like Sonarr or Radarr, its main focus is on post-processing and organization, rather than downloading.

## Features
* Automatically scan and post-process your game collection, with options to verify it by hash or name
* Scrape multiple websites, including screenscraper.fr, igdb.com, store.steampowered.com, mobygames.com, emumovies.com, and more, to provide comprehensive game information
* Centralize all your data on your NAS, enabling multiple clients to play without data duplication
* Enjoy multi-user support with save-game synchronization (requires emulator-support)
* Effortlessly reconfigure emulator settings, such as controller, video, and multiplayer, from the API (requires emulator-support)
* Benefit from an Admin UI for editing scraped information or manually adding games
* Run RetroBox API in Docker, using a SQLite database for maximum efficiency.

## Progress
I'm currently determining how rom management should work. Using DAT files would be ideal as they provide hashes and a list of games for most retro consoles. Supporting 1G1R would prevent drowning in multiple versions and reduce storage requirements. I'm exploring how to modify and use these DAT files to enable easy drag-and-drop functionality into a database directory, facilitating loading of desired games into the API's database. Let me know what you think about this idea!

- [ ] Determine how rom management should work
- [ ] Integrate all proof-of-concept code into an initial system  
...

## Client
The client is still in the planning stages.  
I envision a web-based solution, potentially using SvelteKit or another Javascript framework, that can fetch the list of platforms and games from the API. When a user selects a game, the client can then fetch media and detailed information from the API. Upon launching the game, the client can make another request for a bundled download containing the necessary rom/game files and emulator (if required). After the user exits the game, the client can extract the save game from the emulator directory and upload it to the API using the user's credentials.

## Roadmap
Although there is no public version of this project available at present, I welcome collaborations.
The API is developed using Python and FastAPI. I'm looking for people familiar with Python/FastAPI, Romsets, emulators or automation in general.
