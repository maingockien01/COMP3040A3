# Upcoming Concerts in Manitoba
## API Description
#### Topic: an API that provides a list of upcoming concerts in Manitoba.

Our API provides the user with information about upcoming concerts in Manitoba. The user can specify a range of parameters such as a date range, the artist name, or the city name, however, all these parameters are optional. Should a user not specify any of the parameters, they will get a list of all concerts in Manitoba for the upcoming year.

The concert information that is recieved by making a query will contain the city that the concert is occuring in, the name of the artist appearing in the concert, and the date that the concert will take place.

In the case of invalid input such as a date range prior to the current date, or invalid artist or city names, the user will recieve an error specifying the issue.

## Endpoint(s)

`GET /concerts`

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
```
{
    "concerts": [
        {
            "artists": ["Metallica", "Slash"],
            "venueName": "Bell MTS Center",
            "date": "11-21-2021",
            "venueAddress": "223 Carlton St #600, Winnipeg, MB, R3C 0V4",
            "Time": "6:00pm"
        }
    ]
}
```

## Resources

The request is formatted as the above example where the parameters must be given followed by "//api/concerts?", the first parameters are start_date and end_date that must be formatted as \<dd-mm-yyyy\>, followed by the city name and artist name.  
The response is formatted as JSON where the information is displayed in the order:  
* Artist: The artist name as a string
* Venue Name: The venue name as a string
* Date: A string that represensts the date in the format \<dd-mm-yyyy\>
* Venue Address: A string that represents the address of the venue in the format {\<Street Adress>, \<City Name\>, \<Province\>, \<Postal Code\>}
* Time: A string that represents the start time of the concert in the format {\<hh:mm\>\<am/pm\>}


## Group Members

* Akshay Sharma
* Kien Mai
* Haseeb Paracha
* Farhan Akib Rahman
* Zhijie Zheng
