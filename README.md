# Upcoming Concerts in Manitoba
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

If no parameter is specified in a request, as default, the api will return a respond that lists all upcoming concerts in Manitoba in 1 year from today.

## Sample Request
```
https://api.concertMB.ca/concerts
https://api.concertMB.ca/concerts?
https://api.concertMB.ca/concerts?

```
## Sample Response

## Resources

[SongKick](https://www.songkick.com/developer/upcoming-events-for-metro-area)  
This API finds out upcoming events in a specific metro area. A metro area is a city or a group of cities used by Songkick to alert users to concerts in their region.

## Group Members

* Akshay Sharma
* Kien Mai
* Haseeb Paracha
* Farhan Akib Rahman
* Zhijie Zheng
