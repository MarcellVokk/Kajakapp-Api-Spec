---
title: Default module
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: "@tarslib/widdershins v4.0.30"

---

# Default module

Base URLs:

# Authentication

# Default

## GET Get Competition Info

GET /api/competition

Retrive basic information and the list of races in this competition.

> Response Examples

> 200 Response

```json
{
  "competition": {
    "name": "Olympic Hopes Regatta",
    "location": "Poznan, Poland",
    "firstDay": 1694037600,
    "lastDay": 1694383199
  },
  "races": [
    {
      "id": "1.0",
      "name": "K1 Men 1000m U17",
      "round": "Heat 1",
      "isBest": false,
      "boat": "K1",
      "distance": "1000m",
      "start": 1694068200,
      "note": "",
      "progression": "1-4 + 3x5th BT to SF, rest out"
    },
    {
      "id": "1.0",
      "name": "K1 Men 1000m U17",
      "round": "Heat 1",
      "isBest": false,
      "boat": "K1",
      "distance": "1000m",
      "start": 1694068200,
      "note": "",
      "progression": "1-4 + 3x5th BT to SF, rest out"
    }
  ]
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» competition|[Competition](#schemacompetition)|true|none||none|
|»» name|string|true|none|The name of the competition.|The name of the competition. Note: In english.|
|»» location|string|true|none|The location of the competition.|The location of the competition. Note: In english.|
|»» firstDay|integer|true|none|The start date of the competition.|The start date of the competition. Note: In Unix time seconds format.|
|»» lastDay|integer|true|none|The end date of the competition.|The end date of the competition. Note: In Unix time seconds  format.|
|» races|[[Race](#schemarace)]|true|none||none|
|»» id|string|true|none|The id of the race.|The id of the race. Note: This can be any string in any format, but it needs to be able to uniquely identify a race within this competition.|
|»» name|string|true|none|The name of the race, not including the round.|The name of the race, not including the round. (eg.: correct: "K1 Men 1000m U17", incorrect: "K1 Men 1000m U17 - Heat 1")|
|»» round|string|true|none|The round name of the race.|The round name of the race.|
|»» isBest|boolean|true|none|True if this race is the best final.|True if this race is the best final. Note: True if this race was the best final of a series (eg.: Final A), and the series has a medal ceremony.|
|»» boat|string|true|none|The boat type of the race.|The boat type of the race.|
|»» distance|string|true|none|The distance of the race.|The distance of the race. Note: In meters or in kilometers (only mark unit with 'm' or 'km'). Do not put space between number and unit (eg.: correct: "1000m", incorrect: "1000 m"). Only use ',' for marking the decimal point. (eg.: correct: "3,6km", incorrect: "3.6km").|
|»» start|integer|true|none|The precise start date and time of the race.|The precise start date and time of the race. Note: In Unix time seconds format.|
|»» note|string|true|none|The note for this race.|The note for this race. Note: If there is no note attached to this race, leave this field empty, do not poppulate with placeholder text like "No note", etc...|
|»» progression|string|true|none|The progression scheme of this race.|The progression scheme of this race. Note: If this race doesn't have a progression scheme, leave this field empty, do not poppulate with placeholder text like "No progression", etc...|

## GET Get Race Info

GET /api/race

Retrive info and the startlist/results of this race

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|raceId|query|string| no |The id of the race.|

> Response Examples

> 200 Response

```json
{
  "race": {
    "id": "1.0",
    "name": "K1 Men 1000m U17",
    "round": "Heat 1",
    "isBest": false,
    "boat": "K1",
    "distance": "1000m",
    "start": 1694068200,
    "note": "",
    "progression": "1-4 + 3x5th BT to SF, rest out"
  },
  "boats": [
    {
      "number": "5",
      "finishPosition": "1",
      "finishTime": "03:45.045",
      "finishTimeDelta": "10.69",
      "athletes": [
        {
          "kajakappId": "",
          "icfId": "133328",
          "name": "Gazdag Marcell Zsolt",
          "birthYear": "2007",
          "nation": "HUN"
        }
      ]
    },
    {
      "number": "5",
      "finishPosition": "1",
      "finishTime": "03:45.045",
      "finishTimeDelta": "10.69",
      "athletes": [
        {
          "kajakappId": "",
          "icfId": "133328",
          "name": "Gazdag Marcell Zsolt",
          "birthYear": "2007",
          "nation": "HUN"
        }
      ]
    }
  ]
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» race|[Race](#schemarace)|true|none||none|
|»» id|string|true|none|The id of the race.|The id of the race. Note: This can be any string in any format, but it needs to be able to uniquely identify a race within this competition.|
|»» name|string|true|none|The name of the race, not including the round.|The name of the race, not including the round. (eg.: correct: "K1 Men 1000m U17", incorrect: "K1 Men 1000m U17 - Heat 1")|
|»» round|string|true|none|The round name of the race.|The round name of the race.|
|»» isBest|boolean|true|none|True if this race is the best final.|True if this race is the best final. Note: True if this race was the best final of a series (eg.: Final A), and the series has a medal ceremony.|
|»» boat|string|true|none|The boat type of the race.|The boat type of the race.|
|»» distance|string|true|none|The distance of the race.|The distance of the race. Note: In meters or in kilometers (only mark unit with 'm' or 'km'). Do not put space between number and unit (eg.: correct: "1000m", incorrect: "1000 m"). Only use ',' for marking the decimal point. (eg.: correct: "3,6km", incorrect: "3.6km").|
|»» start|integer|true|none|The precise start date and time of the race.|The precise start date and time of the race. Note: In Unix time seconds format.|
|»» note|string|true|none|The note for this race.|The note for this race. Note: If there is no note attached to this race, leave this field empty, do not poppulate with placeholder text like "No note", etc...|
|»» progression|string|true|none|The progression scheme of this race.|The progression scheme of this race. Note: If this race doesn't have a progression scheme, leave this field empty, do not poppulate with placeholder text like "No progression", etc...|
|» boats|[[Boat](#schemaboat)]|true|none||none|
|»» number|string|true|none|The start number (lane) of the boat.|The start number (lane) of the boat. Note: This field should only contain numbers, it shouldn't contain any brackets or such (eg.: correct: "5", incorrect: "[ 5 ]")|
|»» finishPosition|string|true|none|The finish position of the boat.|The finish position of the boat. If the boat did not finish yet, leave empty. If the boat got disqualified, specify abbreviated disqualification reason in this field (eg.: "DNS", "DNF", etc). If the boat finished, specify finish position with numbers only (eg.: correct: "1", incorrect: "1." or "1. place").|
|»» finishTime|string|true|none|The finish time of the boat.|The finish time of the boat. If the boat did not finish yet or if the boat got disqualified, leave empty. Note: Only use '.' for marking the decimal point.|
|»» finishTimeDelta|string|true|none|The finish time difference of the boat from the time of the first boat.|The finish time difference of the boat counted from the finish time of the first boat. If the boat finished in first place or if the boat did not finish yet or if the boat got disqualified, leave empty. Do not prefix the data with characters like '+', only specify the time (eg.: correct: "10.69", incorrect "+10.69"). Note: Only use '.' for marking the decimal point.|
|»» athletes|[[Athlete](#schemaathlete)]|true|none||none|
|»»» kajakappId|string|true|none|The Kajakapp ID of the athlete.|The Kajakapp ID of the athlete, if known.|
|»»» icfId|string|true|none|The ICF ID of the athlete.|The ICF ID of the athlete, if known.|
|»»» name|string|true|none|The full name of the athlete.|The full name of the athlete. Note: Family name first, then middle name, then last name. Use capital letters, do not use commas or full-upper-case segments (eg.: correct: "Gazdag Marcell", incorrect: "Marcell, GAZDAG")|
|»»» birthYear|string|true|none|The birth year of the athlete.|The birth year of the athlete.|
|»»» nation|string|true|none|The nation of the athlete.|The nation of the athlete. Note: Use the nation codes specified by the IOC (International Olympic Committee).|

# Data Schema

<h2 id="tocS_Competition">Competition</h2>

<a id="schemacompetition"></a>
<a id="schema_Competition"></a>
<a id="tocScompetition"></a>
<a id="tocscompetition"></a>

```json
{
  "name": "Olympic Hopes Regatta",
  "location": "Poznan, Poland",
  "firstDay": 1694037600,
  "lastDay": 1694383199
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|name|string|true|none|The name of the competition.|The name of the competition. Note: In english.|
|location|string|true|none|The location of the competition.|The location of the competition. Note: In english.|
|firstDay|integer|true|none|The start date of the competition.|The start date of the competition. Note: In Unix time seconds format.|
|lastDay|integer|true|none|The end date of the competition.|The end date of the competition. Note: In Unix time seconds  format.|

<h2 id="tocS_Race">Race</h2>

<a id="schemarace"></a>
<a id="schema_Race"></a>
<a id="tocSrace"></a>
<a id="tocsrace"></a>

```json
{
  "id": "1.0",
  "name": "K1 Men 1000m U17",
  "round": "Heat 1",
  "isBest": false,
  "boat": "K1",
  "distance": "1000m",
  "start": 1694068200,
  "note": "string",
  "progression": "1-4 + 3x5th BT to SF, rest out"
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|id|string|true|none|The id of the race.|The id of the race. Note: This can be any string in any format, but it needs to be able to uniquely identify a race within this competition.|
|name|string|true|none|The name of the race, not including the round.|The name of the race, not including the round. (eg.: correct: "K1 Men 1000m U17", incorrect: "K1 Men 1000m U17 - Heat 1")|
|round|string|true|none|The round name of the race.|The round name of the race.|
|isBest|boolean|true|none|True if this race is the best final.|True if this race is the best final. Note: True if this race was the best final of a series (eg.: Final A), and the series has a medal ceremony.|
|boat|string|true|none|The boat type of the race.|The boat type of the race.|
|distance|string|true|none|The distance of the race.|The distance of the race. Note: In meters or in kilometers (only mark unit with 'm' or 'km'). Do not put space between number and unit (eg.: correct: "1000m", incorrect: "1000 m"). Only use ',' for marking the decimal point. (eg.: correct: "3,6km", incorrect: "3.6km").|
|start|integer|true|none|The precise start date and time of the race.|The precise start date and time of the race. Note: In Unix time seconds format.|
|note|string|true|none|The note for this race.|The note for this race. Note: If there is no note attached to this race, leave this field empty, do not poppulate with placeholder text like "No note", etc...|
|progression|string|true|none|The progression scheme of this race.|The progression scheme of this race. Note: If this race doesn't have a progression scheme, leave this field empty, do not poppulate with placeholder text like "No progression", etc...|

<h2 id="tocS_Boat">Boat</h2>

<a id="schemaboat"></a>
<a id="schema_Boat"></a>
<a id="tocSboat"></a>
<a id="tocsboat"></a>

```json
{
  "number": "5",
  "finishPosition": "1",
  "finishTime": "03:45.045",
  "finishTimeDelta": "10.69",
  "athletes": [
    {
      "kajakappId": "KJKAPFDFE7E45F2954354965272AA74E9C0D4",
      "icfId": "133328",
      "name": "Gazdag Marcell Zsolt",
      "birthYear": "2007",
      "nation": "HUN"
    }
  ]
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|number|string|true|none|The start number (lane) of the boat.|The start number (lane) of the boat. Note: This field should only contain numbers, it shouldn't contain any brackets or such (eg.: correct: "5", incorrect: "[ 5 ]")|
|finishPosition|string|true|none|The finish position of the boat.|The finish position of the boat. If the boat did not finish yet, leave empty. If the boat got disqualified, specify abbreviated disqualification reason in this field (eg.: "DNS", "DNF", etc). If the boat finished, specify finish position with numbers only (eg.: correct: "1", incorrect: "1." or "1. place").|
|finishTime|string|true|none|The finish time of the boat.|The finish time of the boat. If the boat did not finish yet or if the boat got disqualified, leave empty. Note: Only use '.' for marking the decimal point.|
|finishTimeDelta|string|true|none|The finish time difference of the boat from the time of the first boat.|The finish time difference of the boat counted from the finish time of the first boat. If the boat finished in first place or if the boat did not finish yet or if the boat got disqualified, leave empty. Do not prefix the data with characters like '+', only specify the time (eg.: correct: "10.69", incorrect "+10.69"). Note: Only use '.' for marking the decimal point.|
|athletes|[[Athlete](#schemaathlete)]|true|none||none|

<h2 id="tocS_Athlete">Athlete</h2>

<a id="schemaathlete"></a>
<a id="schema_Athlete"></a>
<a id="tocSathlete"></a>
<a id="tocsathlete"></a>

```json
{
  "kajakappId": "KJKAPFDFE7E45F2954354965272AA74E9C0D4",
  "icfId": "133328",
  "name": "Gazdag Marcell Zsolt",
  "birthYear": "2007",
  "nation": "HUN"
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|kajakappId|string|true|none|The Kajakapp ID of the athlete.|The Kajakapp ID of the athlete, if known.|
|icfId|string|true|none|The ICF ID of the athlete.|The ICF ID of the athlete, if known.|
|name|string|true|none|The full name of the athlete.|The full name of the athlete. Note: Family name first, then middle name, then last name. Use capital letters, do not use commas or full-upper-case segments (eg.: correct: "Gazdag Marcell", incorrect: "Marcell, GAZDAG")|
|birthYear|string|true|none|The birth year of the athlete.|The birth year of the athlete.|
|nation|string|true|none|The nation of the athlete.|The nation of the athlete. Note: Use the nation codes specified by the IOC (International Olympic Committee).|

