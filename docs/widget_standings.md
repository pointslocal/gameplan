# Widget: Standings
> This widget produces ordered standings for teams by conference.

##### Instantiation
```javascript
  var widget = new Gameplan(*OPTIONS*);
  widget.standings(*STANDINGS OPTIONS*, *DOM ELEMENT SELECTOR*, *TEMPLATE CODE*);
```

##### Global Options
- site **[ string ]** - Your site code

##### Standings Options
- sport **[ string ]** - Sport name or GUID
- season **[ string ]** - Season name or GUID
- conference **[ string ]** - Conference GUID or name
- sortby **[ string ]** - Sort field (team_name, overall_wins, overall_losses, conference_wins, conference_losses)
- sortorder **[ string ]** - Sort order (asc, desc)

##### Return Variables
- **conference_name** - Name of conference
- **conference_guid** - GUID of conference
- **season** - Name of season
- **season_guid** - Season's GUID
- **teams** - Array containing teams
    - **team_name**
    - **team_guid**
    - **team_mascot**
    - **team_overall_wins**
    - **team_overall_losses**
    - **team_overall_winpct**
    - **team_conference_wins**
    - **team_conference_losses**
    - **team_conference_winpct**

## Example:
```javascript
  var widget = new Gameplan({'site':'madison'});
  widget.standings({ 'sport': 'football', 'conference': 'east', 'sortby': 'overall_wins', 'sort_order': 'desc' }, '#myElement', "<h2>Standings</h2><table>{{teams.each}}<tr><td><a href='http://madison.pointslocal.com/schools/{{school_guid}}/{{sport_guid}}'>{{team_name}}</a></td><td>{{team_overall_wins}}</td><td>{{team_overall_losses}}</td><td>{{team_conference_wins}}</td><td>{{team_conference_losses}}</td></tr>{{/teams.each}}</table>");
```