# Widget: Teams
> Returns one or more team with image and meta data

##### Instantiation
```javascript
  var widget = new Gameplan(*OPTIONS*);
  widget.teams(*SCHEDULE OPTIONS*, *DOM ELEMENT SELECTOR*, *TEMPLATE CODE*);
```

##### Global Options
- site **[ string ]** - Your site code

##### Schedule Options
- sport **[ string ]** - Sport name or GUID
- count **[ int ]** - Number of results to return
- school **[ string ]** - School's name or internal GUID
- image_width **[ int ]** - Width in pixels for image (defaults to 200)
- image_height **[ int ]** - Height in pixels for image (defaults to 200)

##### Return Variables
- **teams** - Array of teams
    - **team_name**
    - **team_guid**
    - **team_logo_url**
    - **meta** - Array of meta data fields
        - **name** - Name of meta field
        - **value** - Value of meta field

## Example:
```javascript
  var widget = new Gameplan({'site':'madison'});
  widget.teams({ 'sport': 'football', 'school': 'madison-edgewood' }, '#myElement', "<h2>About Madison Edgewood</h2><img src="{{team_logo_url}}" />{{meta.each}}{{name}}:{{value}}{{/meta.each}}");
```