# Widget: Conferences
> This widget produces a list of conferences.

##### Instantiation
```javascript
  var widget = new Gameplan(*OPTIONS*);
  widget.conferences(*STANDINGS OPTIONS*, *DOM ELEMENT SELECTOR*, *TEMPLATE CODE*);
```

##### Global Options
- site **[ string ]** - Your site code

##### Standings Options
- sport **[ string ]** - Sport name or GUID
- count **[ int ]** - Number of conferences to return

##### Return Variables
- **conference_name** - Name of conference
- **conference_guid** - GUID of conference

## Example:
```javascript
  var widget = new Gameplan({'site':'madison'});
  widget.conferences({ 'sport': 'football', 'count':50 }, '#myElement', "<h2>Conferences</h2><table>{{items.each}}<tr><td><a href='http://madison.pointslocal.com/conferences/{{conference_guid}}'>{{conference_name}}</a></td></tr>{{/items.each}}</table>");
```