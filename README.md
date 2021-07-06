# WeatherApplication
Weather Application to integrate apis with https://openweathermap.org/ so that we can get the current weather by city ot lat long

This project is a simple Java Based application applying some Business conditions which as per the following logic:

- User can get the weather by the city and country. The request will be the city name followed by the country name in ISO code separated by a Comma.
- User can get the weather by the latitude and longitude. 
- Cached data should be reset every 2 hours

### Note-> I have attached the postman collection in resources folder (WeatherSystem.postman_collection.json) which can be used for reference.

Assumptions :
- API key needs to be created for integrating the openweathermap for this assignment.My app id is "79be99a36b3b79edb3082702fea7f283".
- Complete cache data should be reset every 2 hours. I have used a Cron scheduler to do the same.

### API Details:

- 1.> The openweathermap api

	URL :http://api.openweathermap.org/data/2.5/weather?appid=79be99a36b3b79edb3082702fea7f283&q=Dubai,AE
	METHOD : GET
	PARAMS : 
	1.> appid : 79be99a36b3b79edb3082702fea7f283
	2.> q : Dubai,AE

- 2.> The Get Weather api by City and Country

	URL : http://localhost:8080/api/weather/getbycitycountry?citycountry=Dubai,AE
	METHOD : GET
	HEADERS: Content-Type : application/json
	PARAMS : 
	1.> citycountry : Dubai,AE

- 3.> The Get Weather api by latitude and longitude

	URL : http://localhost:8080/api/weather/getbylatlon?lat=25.3220&lon=55.3865
	METHOD : GET
	HEADERS: Content-Type : application/json
	PARAMS : 
	1.> lat : 25.3220
	2.> lon : 55.3865

##### Note: In order to run the project, kindly download the source code and run the WeatherApplication class
 
## Requirements

For building and running the application you need:

- [JDK 1.8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
- [Maven 3](https://maven.apache.org)

## Approach Discussion

It's a stand alone application consist of all Possible test cases. Following are the approach has been taken to address this assignment

1. Designed in a way that both the use cases can be tested independently.
2. Created a scheduler which will reset weather data every 2 hours.

## How to Run

	Run the WeatherApplication class and call the rest GET api 
	"http://localhost:8080/api/weather/getbycitycountry?citycountry=Dubai,AE" or 
	"http://localhost:8080/api/weather/getbylatlon?lat=25.3220&lon=55.3865"

## How to get Coverage
```shell
mvn clean install
```
it will generate coverage reports in WeatherSystem\target\site\jacoco
Open index.html

