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
| start_date | string | NO | start date of time range |
| end_date | string | NO | end date of time range |
| city_name | string | NO | city name to base search on |
| artist | string | NO | artist participates in concerts |

If no parameter is specified in a request, the api will return a respond that lists all upcoming concerts in Manitoba in 1 year from the current day as default.

## Sample Request
```
https://api.concertMB.ca/concerts
https://api.concertMB.ca/concerts?
https://api.concertMB.ca/concerts?

```
## Sample Response

The response is formatted using JSON. An example:

## Resources


## Group Members

* Akshay Sharma
* Kien Mai
* Haseeb Paracha
* Farhan Akib Rahman
* Zhijie Zheng
