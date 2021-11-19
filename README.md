# Group 7 A3
## API Description
- Topic: an API that provides a list of upcoming concerts in Manitoba.


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

## Resources

https://www.songkick.com/developer/upcoming-events-for-metro-area

## Group Members

**Members** 
* Akshay Sharma
* Kien Mai
* Haseeb Paracha
* Farhan Akib Rahman
* Zhijie Zheng
