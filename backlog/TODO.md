- Consider new sources of ratings
  - Gamespot
  - IGN
  - Humble Store
  - Amazon
  - GOG - might not be viable due to the js search implementation
- For HowLongToBeat, pull more than just 'Main Story', to handle cases like id
  7236, which has info for 'Main + Extras' and 'Completionist', but not the
  'Main Story'
- For imdb, revamp the script to function like the rest, where you can
  manually set the title id and let it grab the rating

## Wrappers

- Delete Planetside 2. The MMOFPS is now dead.
- Finish fixing SotS

# Rework

- Add score-title to game-scores.toml to speed up the detailed display of the
  score script
- Add a script (or argument to an existing script) to simply examine all the
  stores and titles associated with a given game, i.e. use the info in
  game-scores.toml to query scoring.toml for full information. I could
  potentially just add an argument to score to show full details.
- Add howlongtobeat data to game-scores.toml and potentially rename the file
  to more accurately reflect its purpose. Potentially put the info in
  scoring.toml and rename, otherwise add a new toml.
- Change the scoring methods to stop skipping zero/tbd scores, so matching
  identifiers still get recorded in scoring.toml and game-scores.toml, just
  those scores won't be included by set-score-info. This way we can update
  the scores for them in case scores get added on the sites eventually.
  - Pro Pinball Timeshock! for example is on itad, metacritic, gog, and
    amazon, but itad/metacritic have no scores yet
- Add arguments to search:
  - Include all, not just the first 5 from each search method
- Add arguments to score:
  - Re-score games without scores rather than skipping them
  - Add argument for alternate query string
