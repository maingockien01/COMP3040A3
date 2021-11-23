# Upcoming Concerts in Manitoba
## API Description
#### Topic: an API that provides a list of upcoming concerts in Manitoba.

Our API provides the user with information about upcoming concerts in Manitoba. The user can specify a range of parameters such as a date range, the artist name, or the city name, however, all these parameters are optional. Should a user not specify any of the parameters, they will get a list of all concerts in Manitoba for the upcoming year.

The concert information that is recieved by making a query will contain the city that the concert is occuring in, the name of the artist appearing in the concert, and the date that the concert will take place.

In the case of invalid input such as a date range prior to the current date, or invalid artist or city names, the user will recieve an error specifying the issue.

## Endpoint(s)

```
GET /concerts
```

List all concerts in Manitoba given time range, city name and participating artisits.

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| start_date (mm-dd-yyyy) | string | NO | start date of time range |
| end_date (mm-dd-yyyy) | string | NO | end date of time range |
| city_name | string | NO | city name to base search on |
| artist | string | NO | artist participates in concerts |

If no parameter is specified in a request, the api will return a respond that lists all upcoming concerts in Manitoba in 1 year from the current day as default.

## Example Request
The following request samples are provided in **NodeJS**
```
curl -H "Content-Type:application/json" -X GET "https://api/concerts?start_date=11-20-2021&end_date=11-23-2021&city_name=Winnipeg&artist=Metallica"
```
## Example Response
The response is formatted using **JSON**

Response code: `200`

```
{
    "concerts": [
        {
            "artists": ["Metallica", "Slash"],
            "venueName": "Bell MTS Center",
            "date": "11-21-2021",
            "venueAddress": "223 Carlton St #600, Winnipeg, MB R3C 0V4",
            "Time": "6pm"
        }
    ]
}
```

Response code: `400`

```
{
    "status": "Failure",
    "reason": "BadRequest",
    "message": "The user issued a faulty request. Please check the parameters and try again"
}
```

Response code: `500`

```
{
    "status": "Failure"
    "reason": "InternalServerError",
    "message": "An unexpected error occurred.",
}
```

## Resources


## Group Members

* Akshay Sharma
* Kien Mai
* Haseeb Paracha
* Farhan Akib Rahman
* Zhijie Zheng
