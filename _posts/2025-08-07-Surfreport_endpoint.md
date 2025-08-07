---
title: Surfreport endpoint
date: YYYY-MM-DD HH:MM:SS +/- 0800
categories: [writing sample, api docs]
tags: [api docs]     # TAG names should always be lowercase
---
# SurfREPORTLSKDJTGPLKDJF
Contains information about surfing conditions, including the surf height, wind speed, water temperature, and tide. Also provides a recommendation about whether or not to go surfing.

# Endpoints
`GET` **/surfreport/{beachId}**
Gets the surfing conditions for a specific beach ID.

# Parameters
## Path parameters
| Path parameter | Description                                                                                                                       |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| {beachId}      | The value for the beach you want to look up. The list of beaches is available at https://example.com/surfreport/beaches_available |

## Query string
| Query parameter | Optional or Required | Type                                        | Description                                                                                                                                        |
| --------------- | -------------------- | ------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| Days            | Optional             | Integer                                     | The number of days to include in the response. Default value is 3 and maximum value is 7.                                                          |
| Units           | Optional             | String                                      | The unit of measurement for the response. Imperial returns values in feet and knots. Metric returns values in centimeters and kilometers per hour. |
| Time            | Optional             | Integer. Unix format (ms since 1970 in UTC) | If you include the time, the response only includes the surf condition for the hour specified.                                                     |

# Sample request
`curl -I -X GET "https://api.openweathermap.org/data/2.5/surfreport?zip=95050&appid=APIKEY&units=imperial&days=2"`
(In the above code, replace 'APIKEY' with your actual API key.)

# Sample response
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

## Response definitions
| Item                          | Description                                                                                                                                                                                                                                                                                                                                             | Type    |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- |
| beach                         | The name of the beach you requested according to the `{beachId}`.                                                                                                                                                                                                                                                                                       | String  |
| day                           | The day of the week selected.                                                                                                                                                                                                                                                                                                                           | Object  |
| time                          | The time for the conditions. This item is only included if you include a time parameter in the request.                                                                                                                                                                                                                                                 | String  |
| `{day}/{time}`/tide           | The level of tide at the beach for a specific day and time. Tide is the distance inland that the water rises to. Positive numbers indicate the tide is higher inland. Negative numbers indicate that the tide is out toward the sea. The 0 point reflects the line when a tide is neither going in nor out but is in transition between the two states. | Integer |
| `{day}/{time}`/wind           | The wind speed at the beach, measured in knots (nautical miles per hour). Wind affects the surf height and general wave conditions. Wind speeds of more than 15 knots make surf conditions undesirable because the wind creates white caps and choppy waters.                                                                                           | Integer |
| `{day}/{time}`/watertemp      | The temperature of the ocean water, returned in Fahrenheit or Celcius depending on the unit of measurement you specified. Water temperatures below 70 F usually require wearing a wetsuit.                                                                                                                                                              | Integer |
| `{day}/{time}`/surfheight     | The height of the waves, returned in either feet or centimeters depending on the unit of measurement you specified. A minimum surf height of 3 feet is needed for surfing. Surf heights exceeding 10 feet are not safe.                                                                                                                                 | Integer |
| `{day}/{time}`/recommendation | An overall recommendation of whether or not you should go surfing. The recommendation is based on a combination of factors including wind, watertemp, and surfheight. Three responses are possible: (1) "Go surfing!", (2) "Surfing conditions are okay, not great.", and (3) "Not a good day for surfing."                                             | String  |
