# Widget: Schedule / Results
> Creates widgets for schedules, results and individual box scores.

##### Instantiation
```javascript
  var widget = new Gameplan(*OPTIONS*);
  widget.results(*SCHEDULE OPTIONS*, *DOM ELEMENT SELECTOR*, *TEMPLATE CODE*);
```

##### Global Options
- site **[ string ]** - Your site code

##### Schedule Options
- sport **[ string ]** - Sport name or GUID
- count **[ int ]** - Number of results to return
- offset **[ int ]** - Number of results to skip, useful for pagination
- school **[ string ]** - School's name or internal GUID
- date **[ string ]** - Date of games or 'latest', 'next' or 'today-recent'.  See API docs /api/games for more detail.
- conference **[ string ]** - Conference for games
- game_id **[ int ]** - Restricts results to a single game


##### Return Variables
- **winning_name** - Name of winning team
- **winning_guid** - GUID of winning team
- **winning_score** - Winning team's final score
- **losing_name** - Name of losing team
- **losing_guid** - GUID of losing team
- **losing_score** - Losing team's final score
- **away_name** - Name of away team
- **away_guid** - GUID of away team
- **away_score** - Away team's final score
- **away_periods** - Array of away team's period scores
- **home_name** - Name of home team
- **home_guid** - GUID of home team
- **home_score** - Home team's final score
- **home_periods** - Home team's period scores
- **date** - Date of game
- **time** - Time of game
- **complete** - True/false if game is complete

## Example:
```javascript
  var widget = new Gameplan({'site':'madison'});
  widget.results({ 'sport': 'football', 'count': 5, 'date': 'latest' }, '#myElement', "<h2>Latest Results</h2><table>{{items.each}}<tr><td><a href='http://madison.pointslocal.com/scores/{{game_id}}'>{{winner_name}} {{winner_score}}, {{loser_name}} {{loser_score}}</a></td></tr>{{/items.each}}</table>");
```