# /api/v1/games

##### Request Parameters
- date **[ string ]** - Return games by date in MM/DD/YYYY format (can also accept 'next' or 'last')

##### Response Parameters
- guid **[ string ]** - Games internal GUID
- game_id ** [ int ]** - Integer ID of game, for requesting games by ID

## /api/v1/games/[:id]
Requests a specific game