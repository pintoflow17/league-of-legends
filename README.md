# League Of Legends (Esports)

## Introduction

**League Of Legends (Esports) API** provides instant access to everything you need for LoL Esports: leagues, matches, players, live scores, tournaments, schedules, and more. Whether you're looking for VODs, team information, or detailed stats, we have you covered.

## Authentication

The URL you need to use is the following: `https://league-of-legends-esports1.p.rapidapi.com/`
The API requires the headers listed below:

- **`x-rapidapi-host`**: `league-of-legends-esports1.p.rapidapi.com`
- **`x-rapidapi-key`**: `YOUR_API_KEY`

Make sure to replace `YOUR_API_KEY` with your API key. You can register one [here](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/league-of-legends-esports1/pricing).
Some frameworks automatically add extra headers, you have to make sure to remove them in order to get a response from the API.

## Endpoints

The API is configured to accept only **GET** requests. Below are the available endpoints with their descriptions and required parameters.

### 1. **`GET /leagues`**

- **Description**: Fetches all available leagues.

Example request:

```javascript
fetch('https://league-of-legends-esports1.p.rapidapi.com/leagues', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'league-of-legends-esports1.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "leagues": [
    {
      "leagueId": "98767975604431411",
      "slug": "worlds",
      "name": "Worlds",
      "region": "INTERNATIONAL",
      "image": "http://static.lolesports.com/leagues/1592594612171_WorldsDarkBG.png",
      "priority": 1,
      "url": "https://lolesports.com/teams/worlds"
    },
    {
      "leagueId": "98767991299243165",
      "slug": "lcs",
      "name": "LCS",
      "region": "NORTH AMERICA",
      "image": "http://static.lolesports.com/leagues/1706356907418_LCSNew-01-FullonDark.png",
      "priority": 1,
      "url": "https://lolesports.com/teams/lcs"
    },
    {
      "leagueId": "98767991302996019",
      "slug": "lec",
      "name": "LEC",
      "region": "EMEA",
      "image": "http://static.lolesports.com/leagues/1592516184297_LEC-01-FullonDark.png",
      "priority": 1,
      "url": "https://lolesports.com/teams/lec"
    },
    {
      ...
```

### 2. **`GET /live`**

- **Description**: Retrieves current live game data.

Example request:

```javascript
fetch('https://league-of-legends-esports1.p.rapidapi.com/live', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'league-of-legends-esports1.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "schedule": {
    "events": []
  }
}
```

### 3. **`GET /schedule`**

- **Description**: Retrieves the schedule for a specific league.

| Parameter  | Type   | Default | Description                            | Required |
|------------|--------|---------|----------------------------------------|----------|
| `leagueId` | string | -       | The ID of the league                   | Yes      |

Example request:

```javascript
fetch('https://league-of-legends-esports1.p.rapidapi.com/schedule?leagueId=98767991302996019', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'league-of-legends-esports1.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "startTime": "2024-03-31T18:00:00Z",
    "state": "completed",
    "type": "match",
    "blockName": "Playoffs",
    "league": {
      "name": "LEC",
      "slug": "lec"
    },
    "match": {
      "id": "111997906552170266",
      "flags": [
        "hasVod"
      ],
      "teams": [
        {
          "name": "G2 Esports",
          "code": "G2",
          "image": "http://static.lolesports.com/teams/G2-FullonDark.png",
          "result": {
            "outcome": "win",
            "gameWins": 2
          },
          "record": {
            "wins": 4,
            "losses": 0
          }
        },
        {
          ...
```

### 4. **`GET /tournaments`**

- **Description**: Retrieves tournaments for a specific league.

| Parameter  | Type   | Default | Description                            | Required |
|------------|--------|---------|----------------------------------------|----------|
| `leagueId` | string | -       | The ID of the league                   | Yes      |

Example request:

```javascript
fetch('https://league-of-legends-esports1.p.rapidapi.com/tournaments?leagueId=98767991302996019', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'league-of-legends-esports1.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "tournaments": [
      {
        "id": "112869331703771902",
        "slug": "lec_season_finals_2024",
        "startDate": "2024-08-10",
        "endDate": "2024-09-01"
      },
      {
        "id": "112352881163915249",
        "slug": "lec_summer_2024",
        "startDate": "2024-06-08",
        "endDate": "2024-07-28"
      },
      {
        "id": "111997906550466231",
        "slug": "lec_spring_2024",
        "startDate": "2024-03-08",
        "endDate": "2024-04-15"
      },
      {
        "id": "111560983131400452",
        "slug": "lec_winter_2024",
        "startDate": "2024-01-12",
        "endDate": "2024-02-19"
      },
      {
        "id": "110848560874526298",
        "slug": "lec_season_finals_2023",
        ...
```

### 5. **`GET /standings`**

- **Description**: Retrieves standings for a specific tournament.

| Parameter      | Type   | Default | Description                            | Required |
|----------------|--------|---------|----------------------------------------|----------|
| `tournamentId` | string | -       | The ID of the tournament               | Yes      |

Example request:

```javascript
fetch('https://league-of-legends-esports1.p.rapidapi.com/standings?tournamentId=109466537705744120', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'league-of-legends-esports1.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "standings": [
    {
      "stages": [
        {
          "id": "109466537706530553",
          "name": "Regular Season",
          "type": null,
          "slug": "regular_season",
          "sections": [
            {
              "name": "Regular Season",
              "matches": [
                {
                  "id": "109466537707316992",
                  "state": "completed",
                  "previousMatchIds": [],
                  "flags": [
                    "hasVod"
                  ],
                  "teams": [
                    {
                      "id": "101383793572656373",
                      "slug": "giantx-lec",
                      "name": "GIANTX",
                      "code": "GX",
                      "image": "http://static.lolesports.com/teams/1704790322129_GX.png",
                      "result": {
                        "outcome": "loss",
                        "gameWins": 0
                        ...
```

### 6. **`GET /standingsV3`**

- **Description**: Retrieves updated version (V3) of standings for a specific tournament.

| Parameter      | Type   | Default | Description                            | Required |
|----------------|--------|---------|----------------------------------------|----------|
| `tournamentId` | string | -       | The ID of the tournament               | Yes      |

Example request:

```javascript
fetch('https://league-of-legends-esports1.p.rapidapi.com/standingsV3?tournamentId=109466537705744120', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'league-of-legends-esports1.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "standings": [
    {
      "id": "109466537705744120",
      "name": "Winter 2023",
      "slug": "lec_winter_2023",
      "scores": [
        {
          "team": {
            "id": "98767991926151025",
            "name": "G2 Esports",
            "image": "http://static.lolesports.com/teams/G2-FullonDark.png",
            "code": "G2"
          },
          "position": 1,
          "points": 120
        },
        {
          "team": {
            "id": "103461966965149786",
            "name": "MAD Lions KOI",
            "image": "http://static.lolesports.com/teams/1631819614211_mad-2021-worlds.png",
            "code": "MDK"
          },
          "position": 2,
          "points": 100
        },
        {
          "team": {
            "id": "101383793574360315",
            ...
```

### 7. **`GET /completedEvents`**

- **Description**: Retrieves completed events for a specific tournament.

| Parameter      | Type   | Default | Description                            | Required |
|----------------|--------|---------|----------------------------------------|----------|
| `tournamentId` | string | -       | The ID of the tournament               | Yes      |

Example request:

```javascript
fetch('https://league-of-legends-esports1.p.rapidapi.com/completedEvents?tournamentId=109466537705744120', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'league-of-legends-esports1.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "schedule": {
    "events": [
      {
        "startTime": "2023-01-21T17:00:00Z",
        "blockName": "Week 1",
        "league": {
          "name": "LEC"
        },
        "match": {
          "id": "109466537707316992",
          "type": "normal",
          "teams": [
            {
              "name": "GIANTX",
              "code": "GX",
              "image": "http://static.lolesports.com/teams/1704790322129_GX.png",
              "result": {
                "gameWins": 0
              }
            },
            {
              "name": "G2 Esports",
              "code": "G2",
              "image": "http://static.lolesports.com/teams/G2-FullonDark.png",
              "result": {
                "gameWins": 1
              }
            }
          ],
          ...
```

### 8. **`GET /eventDetails`**

- **Description**: Retrieves details for a specific event.

| Parameter | Type   | Default | Description                            | Required |
|-----------|--------|---------|----------------------------------------|----------|
| `eventId` | string | -       | The ID of the event                    | Yes      |

Example request:

```javascript
fetch('https://league-of-legends-esports1.p.rapidapi.com/eventDetails?eventId=112523566482611689', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'league-of-legends-esports1.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "event": {
    "id": "112523566482611689",
    "type": "match",
    "tournament": {
      "id": "112523529392628088"
    },
    "league": {
      "id": "98767991299243165",
      "slug": "lcs",
      "image": "http://static.lolesports.com/leagues/1706356907418_LCSNew-01-FullonDark.png",
      "name": "LCS"
    },
    "match": {
      "strategy": {
        "count": 3
      },
      "teams": [
        {
          "id": "111504538396430510",
          "name": "Shopify Rebellion",
          "code": "SR",
          "image": "http://static.lolesports.com/teams/1701424227458_Teams204_Shopify_1632869404072.png",
          "result": {
            "gameWins": 2
          }
        },
        {
          "id": "98926509883054987",
          "name": "Dignitas",
          ...
```

### 9. **`GET /games`**

- **Description**: Retrieves details for a specific game.

| Parameter | Type   | Default | Description                            | Required |
|-----------|--------|---------|----------------------------------------|----------|
| `gameId`  | string | -       | The ID of the game                     | Yes      |

Example request:

```javascript
fetch('https://league-of-legends-esports1.p.rapidapi.com/games?gameId=112523566482677322', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'league-of-legends-esports1.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "games": [
    {
      "id": "112523566482677322",
      "state": "completed",
      "number": 1,
      "vods": [
        {
          "locale": "en-US",
          "mediaLocale": {
            "locale": "en-US",
            "englishName": "English (North America)",
            "translatedName": "English (North America)"
          },
          "parameter": "vumHdrSOsNI",
          "provider": "youtube",
          "offset": 0
        }
      ]
    }
  ]
}
```

### 10. **`GET /teams`**

- **Description**: Retrieves details for a specific team.

| Parameter  | Type   | Default | Description                            | Required |
|------------|--------|---------|----------------------------------------|----------|
| `teamSlug` | string | -       | The slug of the team                   | Yes      |

Example request:

```javascript
fetch('https://league-of-legends-esports1.p.rapidapi.com/teams?teamSlug=dwg-kia', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'league-of-legends-esports1.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "teams": [
    {
      "id": "100725845018863243",
      "slug": "dwg-kia",
      "name": "Dplus Kia",
      "code": "DK",
      "image": "http://static.lolesports.com/teams/1673260049703_DPlusKIALOGO11.png",
      "alternativeImage": "http://static.lolesports.com/teams/1673260049704_DPlusKIALOGO2.png",
      "backgroundImage": "http://static.lolesports.com/teams/DamwonGamingDWG.png",
      "status": "active",
      "homeLeague": {
        "name": "LCK",
        "region": "KOREA"
      },
      "players": [
        {
          "id": "100725844988653773",
          "summonerName": "ShowMaker",
          "firstName": "Su",
          "lastName": "Heo",
          "image": "http://static.lolesports.com/players/1718364886130_DK_Showmaker_784.png",
          "role": "mid"
        },
        {
          "id": "101388913291808185",
          "summonerName": "Kellin",
          "firstName": "Hyeonggyu",
          "lastName": "Kim",
          "image": "http://static.lolesports.com/players/1718364815306_DK_Kellin_784.png",
          ...
```

### 11. **`GET /match-window`**

- **Description**: Retrieves match window details.

| Parameter      | Type   | Default | Description                                                    | Required |
|----------------|--------|---------|----------------------------------------------------------------|----------|
| `gameId`       | string | -       | The ID of the game                                             | Yes      |
| `startingTime` | string | -       | The starting time of the match window ('YYYY-MM-DDTHH:MM:SSZ') | No       |

Example request:

```javascript
fetch('https://league-of-legends-esports1.p.rapidapi.com/match-window?gameId=112523566482677322', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'league-of-legends-esports1.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "esportsGameId": "112523566482677322",
  "esportsMatchId": "112523566482677321",
  "gameMetadata": {
    "patchVersion": "14.14.602.3371",
    "blueTeamMetadata": {
      "esportsTeamId": "98926509885559666",
      "participantMetadata": [
        {
          "participantId": 1,
          "esportsPlayerId": "98767991746528652",
          "summonerName": "TL Impact",
          "championId": "Rumble",
          "role": "top"
        },
        {
          "participantId": 2,
          "esportsPlayerId": "99566404525897139",
          "summonerName": "TL UmTi",
          "championId": "Ivern",
          "role": "jungle"
        },
        {
          "participantId": 3,
          "esportsPlayerId": "105957619949286329",
          "summonerName": "TL APA",
          "championId": "Tristana",
          "role": "mid"
        },
        {
          ...
```

### 12. **`GET /match-details`**

- **Description**: Retrieves detailed information for a specific match.

| Parameter      | Type   | Default | Description                                             | Required |
|----------------|--------|---------|---------------------------------------------------------|----------|
| `gameId`       | string | -       | The ID of the game                                      | Yes      |
| `startingTime` | string | -       | The starting time of the match ('YYYY-MM-DDTHH:MM:SSZ') | No       |

Example request:

```javascript
fetch('https://league-of-legends-esports1.p.rapidapi.com/match-details?gameId=112523566482677322', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'league-of-legends-esports1.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "frames": [
    {
      "rfc460Timestamp": "2024-07-28T22:31:43.260Z",
      "participants": [
        {
          "participantId": 1,
          "level": 1,
          "kills": 0,
          "deaths": 0,
          "assists": 0,
          "totalGoldEarned": 0,
          "creepScore": 0,
          "killParticipation": 0,
          "championDamageShare": 0,
          "wardsPlaced": 0,
          "wardsDestroyed": 0,
          "attackDamage": 0,
          "abilityPower": 0,
          "criticalChance": 0,
          "attackSpeed": 0,
          "lifeSteal": 0,
          "armor": 0,
          "magicResistance": 0,
          "tenacity": 0,
          "items": [],
          "perkMetadata": {
            "styleId": 8200,
            "subStyleId": 8000,
            "perks": [
              ...
```

### 13. **`GET /vods`**

- **Description**: Retrieves video-on-demand content for a specific tournament.

| Parameter      | Type   | Default | Description                            | Required |
|----------------|--------|---------|----------------------------------------|----------|
| `tournamentId` | string | -       | The ID of the tournament               | Yes      |

Example request:

```javascript
fetch('https://league-of-legends-esports1.p.rapidapi.com/vods?tournamentId=107417059262120466', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'league-of-legends-esports1.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "schedule": {
    "events": [
      {
        "startTime": "2022-01-14T17:00:00Z",
        "state": "completed",
        "blockName": "Week 1",
        "league": {
          "name": "LEC"
        },
        "match": {
          "id": "107417059263365721",
          "type": "normal",
          "teams": [
            {
              "name": "MAD Lions KOI",
              "code": "MDK",
              "image": "http://static.lolesports.com/teams/1631819614211_mad-2021-worlds.png",
              "result": {
                "gameWins": 1
              }
            },
            {
              "name": "Team Vitality",
              "code": "VIT",
              "image": "http://static.lolesports.com/teams/1675865863968_Vitality_FullColor.png",
              "result": {
                "gameWins": 0
              }
            }
            ...
```

### 14. **`GET /events`**

- **Description**: Retrieves event list for a specific team.

| Parameter  | Type   | Default | Description                            | Required |
|------------|--------|---------|----------------------------------------|----------|
| `teamSlug` | string | -       | The slug of the team                   | Yes      |

Example request:

```javascript
fetch('https://league-of-legends-esports1.p.rapidapi.com/events?teamSlug=dwg-kia', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'league-of-legends-esports1.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "events": []
}
```

### 15. **`GET /articles`**

- **Description**: Retrieves articles with pagination support.

| Parameter | Type   | Default | Description                            | Required |
|-----------|--------|---------|----------------------------------------|----------|
| `page`    | string | `1`     | The page number for pagination         | No       |
| `perPage` | string | `40`    | The number of articles per page        | No       |

Example request:

```javascript
fetch('https://league-of-legends-esports1.p.rapidapi.com/articles?page=1&perPage=40', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'league-of-legends-esports1.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "articles": [
    {
      "articleId": "9b960443-b69b-4dda-aa56-1c6542c5c731.en-gb",
      "authors": [
        {
          "__typename": "Author",
          "externalTitle": "LoL Esports Staff"
        }
      ],
      "bannerMedia": {
        "__typename": "Image",
        "asset": {
          "__typename": "SanityImageAsset",
          "description": null,
          "label": null,
          "title": null,
          "url": "https://cdn.sanity.io/images/dsfx7636/news/a04fd106ca09673f919cc3e3c95711d9e3e4c2db-1600x900.jpg"
        }
      },
      "description": "The 2024 Worlds Fan Fest will be held October 30-November 1 at Greenwich Peninsula Square in London",
      "externalTitle": "Worlds 2024 Fan Fest Comes to Peninsula Square!",
      "url": "https://lolesports.com/en-US/news/worlds-2024-fan-fest-comes-to-peninsula-square",
      "publishingDates": "2024-10-28T15:00:00.000Z",
      "externalUrl": ""
    },
    {
      "articleId": "9400617e-8c48-4f80-9185-47e4954e5111.en-gb",
      "authors": [
        {
          ...
```

### 16. **`GET /team-statistics`**

- **Description**: Retrieves team statistics for a specific tournament.

| Parameter      | Type   | Default | Description                            | Required |
|----------------|--------|---------|----------------------------------------|----------|
| `tournamentId` | string | -       | The ID of the tournament               | Yes      |

Example request:

```javascript
fetch('https://league-of-legends-esports1.p.rapidapi.com/team-statistics?tournamentId=1177', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'league-of-legends-esports1.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "teamStatisticsByTournament": [
    {
      "team": {
        "id": "333",
        "name": "G2 Esports",
        "acronym": "G2",
        "imageUrl": "https://s-qwer.op.gg/images/lol/teams/333_1672190904241.png",
        "nationality": "DE",
        "foundedAt": "2014-02-24",
        "imageUrlDarkMode": "https://s-qwer.op.gg/images/teams/white/LEC/G2.png",
        "imageUrlLightMode": "https://s-qwer.op.gg/images/lol/teams/g2_light_l.png",
        "youtube": "https://www.youtube.com/FollowGamers2",
        "twitter": "https://twitter.com/G2esports",
        "facebook": "https://www.facebook.com/G2esports",
        "instagram": "https://www.instagram.com/g2esports",
        "discord": "https://discordapp.com/invite/g2esports",
        "website": "https://www.g2esports.com",
        "__typename": "Team"
      },
      "teamId": "333",
      "side": "blue",
      "games": 4,
      "wins": 3,
      "loses": 1,
      "winRate": 0.75,
      "kills": 13.75,
      "deaths": 11.25,
      "assists": 32,
      "goldEarned": 63392,
      ...
```

## Error Handling

The  API returns standard HTTP status codes to indicate the success or failure of API requests. Below are common errors and suggestions for handling them.

|Status Code|Message|Description|Suggested Handling|
|--|--|--|--|
| **400** | Bad Request | The request was malformed or missing required parameters (e.g., `domain` parameter not provided). | Verify that all required parameters are included and correctly formatted. |
| **401** | Unauthorized | Invalid or missing API key in the request headers. | Check that a valid API key is included in `x-rapidapi-key`. |
| **403** | Forbidden | Access to the requested resource is denied, possibly due to rate limits or restricted access. | Review rate limits and ensure API permissions. Retry after a delay if rate limit exceeded. |
| **404** | Not Found | The requested domain information could not be found (e.g., domain does not exist). | Check the spelling or availability of the domain. |
| **429** | Too Many Requests | The API rate limit has been exceeded. | Implement rate-limiting logic and retry after the specified rate limit reset time. |
| **500** | Internal Server Error | A server error occurred while processing the request. | Retry the request after a few seconds. If the error persists, contact API support. |
| **503** | Service Unavailable | The API service is temporarily unavailable (e.g., due to maintenance). | Retry the request later or check the API status page for maintenance alerts. |
