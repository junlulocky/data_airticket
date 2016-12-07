# Airline ticket price dataset

There are two airline ticket price datasets. Dataset1 contains 8 routes, dataset2 contains 12 routes as shown following:

```
dataset1 = ["BCN_BUD",  # route 1
          "BUD_BCN",  # route 2
          "CRL_OTP",  # route 3
          "MLH_SKP",  # route 4
          "MMX_SKP",  # route 5
          "OTP_CRL",  # route 6
          "SKP_MLH",  # route 7
          "SKP_MMX"]  # route 8
```

```
dataset2 = ["BGY_OTP", # route 1
            "BUD_VKO", # route 2
            "CRL_OTP", # route 3
            "CRL_WAW", # route 4
            "LTN_OTP", # route 5
            "LTN_PRG", # route 6
            "OTP_BGY", # route 7
            "OTP_CRL", # route 8
            "OTP_LTN", # route 9
            "PRG_LTN", # route 10
            "VKO_BUD", # route 11
            "WAW_CRL"] # route 12
```

All the files contained in the datasets are in json format. And the data are observed from November 09, 2015 to May 09, 2016. 

## Sample data entry:

```
|-"ArrivalStationCode":"BUD"     # code for the arrival station 
|-"CurrentDate":"30\/12\/2015"   # current date (query date)
|-"Date":"20151230"              # current date (query date)
|-"DepartureStationCode":"BCN"   # code for departure station
|-"Flights":[{
    |-"CarrierCode":"W6"         # NA
    |-"FlightNumber":"2376"      # flight number
    |-"STD":"09:15"              # departure time
    |-"STA":"11:50"              # arrival time
    |-"ArrivalStationName":"Budapest"             # the city name for the arrival station
    |-"DepartureStationName":"Barcelona El Prat"  # the city name for the departure station
    |-"IsMACStation":"True"                       # NA
    |-"IsAirportChange":"False"}]                 # indicator whether need to change (all false in the dataset)
|-"HasSelection":"True"
|-"InMonth":"True"
|-"MinimumPrice":"€49.99"

```

## Sample feature extraction code in python
```
|-sample_data_extraction.py
```

### Extracted feature 1
```
feature 1: flight number -> dummy variables
feature 2: departure date interval from "20151109", because the first observed date is 20151109
feature 3: observed days before departure date
feature 4: minimum price before the observed date
feature 5: maximum price before the observed date
output: the date which has the minimum price from the observed date to departure date is set to 1;
        other entries set to 0
```

### Extracted feature 2
```
feature 1: flight number -> dummy variables
feature 2: departure date interval from "20151109", because the first observed date is 20151109
feature 3: observed days before departure date
feature 4: minimum price before the observed date
feature 5: maximum price before the observed date
output: the ticket price for each entry
```

## Announcement
This dataset is only used for research purpose, you cannot publish for commercial usage. All rights reserved.

## Lincense
MIT
