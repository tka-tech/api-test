# 🤖 Melrose API Test 🤖
Server Engineering Proficiency Test

## Overview:
This test is language agnostic, use whatever you feel best illustrates your style, and use whatever public packages/modules or personal libraries you have available to you. You will have to build a very simple prototype server that solves a specific problem set.  This test also gauges your ability to integrate an utilize existing technology that you may or may not be familiar with.  This test is not timed, but try to keep track of the amount of time you did spend on it, and include a comment in your main source file.  You can send your solution zipped to andrew@theknollagency.com.

## Test
You are tasked with building a real-time, geo-aware inventory system.  The service should return the total available quantity of 1 test product to a consumer. The quantity of that product is based on the sum total of items all drivers have on-hand in a defined region. The region is defined in the corresponding GeoJSON file in this repo. The region has a defined Polygon, with Points representing drivers.  You can create whatever data structures you see fit to solve the problem.

* Use [Redis](https://redis.io/clients) as a data store to help you
* Each driver has an `inventory` property that describes the amount they currently have.   
* You must create at least one API endpoint that accepts a `(application/json)` endcoded request and returns a JSON response below:

```
Request:
{
  "point":[{lng},{lat}]
}

Response:
{
  "sku_1":{quantity} //where quantity is the correct amount
}
```

## Tools
You can load the file into https://geojson.io to visualize your data


## Passing Requirements:
1. Your server runs
2. API Gives the correct level of inventory given the following lng/lat point
3. Given a different initial data set, where some drivers do not reside inside the defined region, the inventory quantity should still be correct (sum of drivers inside the region).
4. Given a point outside the defined region, the API should return an error: {"message":"unavailable at this location"}

## Bonus:
1. Write a test(s) for your solution
2. Make your API product/sku agnostic
3. Make endpoint(s) handling the updating of driver positions.
4. Use any GEO command in redis: [https://redis.io/commands#geo]
5. Give examples of how your solution may not scale well, and what you might do to improve it

Happy Coding!
