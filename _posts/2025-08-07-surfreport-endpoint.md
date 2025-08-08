---
layout: post
title: REST API Documentation Sample
date: '2025-08-07 12:29:05 -0700'
categories: [Writing sample]
tags: [api]     # TAG names should always be lowercase
pin: true
---
This sample was written as part of the [Documenting APIs: a guide for technical writers and engineers](https://idratherbewriting.com/learnapidoc/) course by Tom Johnson.  
This sample is an API reference document for a fictional API resource so the calls do not work.

## Surfreport
Contains information about surfing conditions including the surf height, wind speed, water temperature, and tide. Also provides a recommendation about whether or not to go surfing.

## Endpoints
`GET` <code>/surfreport/{beachId}</code>  
Gets the surfing conditions for a specific beach ID.

## Parameters
### Path parameters
<table>
    <thead>
        <tr>
            <th>Path parameter</th>
            <th>Optional or Required</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>{beachId}</code></td>
            <td>Required</td>
            <td>Integer</td>
            <td>The value for the beach you want to look up. The list of beaches is available at <a href="https://example.com">EXAMPLE BEACH LIST LINK</a> Example: 12345</td>
        </tr>
    </tbody>
</table>

### Query parameters
<table>
    <thead>
        <tr>
            <th>Query parameter</th>
            <th>Optional or Required</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>appid</code></td>
            <td>Required</td>
            <td>Integer</td>
            <td>Your API key. You can request an API key at <a href="https://example.com">EXAMPLE API KEY LINK</a>.</td>
        </tr>
        <tr>
            <td><code>days</code></td>
            <td>Optional</td>
            <td>Integer</td>
            <td>The number of days to include in the response. Default value is 3 and maximum value is 7.</td>
        </tr>
        <tr>
            <td><code>units</code></td>
            <td>Optional</td>
            <td>String</td>
            <td>The unit of measurement for the response. Imperial is the default, and returns values in feet and knots. Metric returns values in centimeters and kilometers per hour.</td>
        </tr>
        <tr>
            <td><code>time</code></td>
            <td>Optional</td>
            <td>Integer. Unix format (ms since 1970 in UTC)</td>
            <td>If you include the time, the response only includes the surf condition for the hour specified. Default returns every hour for each day.</td>
        </tr>
    </tbody>
</table>

## Sample request
`curl "https://api.example.org/data/2.5/surfreport/12345?appid=APIKEY&days=3&units=imperial&time=1754668782"`  
(In the above code, replace 'APIKEY' with your actual API key.)

## Response example
The following is a sample response from the `surfreport\{beachId}` endpoint:  

```json
{
    "surfreport": [
        {
            "beach": "Santa Cruz",
            "monday": {
                "1pm": {
                    "tide": 5,
                    "wind": 15,
                    "watertemp": 60,
                    "surfheight": 5,
                    "recommendation": "Go surfing!"
                },
                "2pm": {
                    "tide": -1,
                    "wind": 1,
                    "watertemp": 50,
                    "surfheight": 3,
                    "recommendation": "Surfing conditions are okay, not great"
                },
                "3pm": {
                	"tide": -1,
                	"wind": 10,
                	"watertemp": 65,
                	"surfheight": 1,
                	"recommendation": "Not a good day for surfing."
                }
                ...

            }
        }
    ]
}
```

### Response
<table>
    <thead>
      <tr>
        <td>Item</td>
        <td>Type</td>
        <td>Description</td>
      </tr>
    </thead>
    <tr>
        <td>beach</td>
        <td>String</td>
        <td>The name of the beach you requested according to the `{beachId}`.</td>
    </tr>
    <tr>
        <td>day</td>
        <td>Object</td>
        <td>The day of the week selected.</td>
    </tr>
    <tr>
        <td>time</td>
        <td>String</td>
        <td>The time for the conditions. This item is only included if you include a time parameter in the request.</td>
    </tr>
    <tr>
        <td><code>{day}/{time}</code>/tide</td>
        <td>Integer</td>
        <td>The level of tide at the beach for a specific day and time. Tide is the distance inland that the water rises to. Positive numbers indicate the tide is higher inland. Negative numbers indicate that the tide is out toward the sea. The 0 point reflects the line when a tide is neither going in nor out but is in transition between the two states.</td>
    </tr>
    <tr>
        <td><code>{day}/{time}</code>/wind</td>
        <td>Integer</td>
        <td>The wind speed at the beach, measured in knots (nautical miles per hour). Wind affects the surf height and general wave conditions. Wind speeds of more than 15 knots make surf conditions undesirable because the wind creates white caps and choppy waters.</td>
    </tr>
    <tr>
        <td><code>{day}/{time}</code>/watertemp</td>
        <td>Integer</td>
        <td>The temperature of the ocean water, returned in Fahrenheit or Celsius depending on the unit of measurement you specified. Water temperatures below 70 F usually require wearing a wetsuit.</td>
    </tr>
    <tr>
        <td><code>{day}/{time}</code>/surfheight</td>
        <td>Integer</td>
        <td>The height of the waves, returned in either feet or centimeters depending on the unit of measurement you specified. A minimum surf height of 3 feet is needed for surfing. Surf heights exceeding 10 feet are not safe.</td>
    </tr>
    <tr>
        <td><code>{day}/{time}</code>/recommendation</td>
        <td>String</td>
        <td>An overall recommendation of whether or not you should go surfing. The recommendation is based on a combination of factors including wind, watertemp, and surfheight. Three responses are possible: (1) "Go surfing!", (2) "Surfing conditions are okay, not great.", and (3) "Not a good day for surfing."</td>
    </tr>
</table>
