# BART-Project---DataVisualization-GeoCalc.

README
http://64.111.127.166/origin-destination/

This data represents BART ridership by origin and destination (O-D) pairs. Each .csv file is compressed into a gz/gzip archive and contains five columns representing Day, Hour, Origin Station, Destination Station, and Trip Count. O-D pairs 
with a trip count of "zero" were ignored during file output to reduce file size. For a list of station name abbreviations visit https://www.bart.gov/sites/default/files/docs/Station_Names.xls

![image](https://github.com/omrbhdr/BART-Project---DataVisualization-GeoCalc./assets/12261537/288e86ae-04b4-45b0-9716-4ca2954a518a)
![image](https://github.com/omrbhdr/BART-Project---DataVisualization-GeoCalc./assets/12261537/c92a061b-d67a-4cf9-83d9-252fb3979c1f)



......................libs........................

      import pandas as pd
      import matplotlib.pyplot as plt
      import numpy as np
      import geopy.distance
      import seaborn as sns
      
...................................................

![image](https://github.com/omrbhdr/BART-Project---DataVisualization-GeoCalc./assets/12261537/77a7a3a6-9613-4da3-8ba5-08588156ff80)
![image](https://github.com/omrbhdr/BART-Project---DataVisualization-GeoCalc./assets/12261537/5d73feef-9d29-4256-a0dd-f08049122cc6)
![image](https://github.com/omrbhdr/BART-Project---DataVisualization-GeoCalc./assets/12261537/34a9c507-569f-4ab7-8e55-09f2223e53e3)
![image](https://github.com/omrbhdr/BART-Project---DataVisualization-GeoCalc./assets/12261537/a33cbca2-fe61-4ac8-b2d1-c31a0ba3e4f6)


  def distance_d(LaA, LaB, LoA, LoB):
# The function "radians" is found in the math module, It's also used to convert radians to degrees.  
    LoA = radians(LoA)  
    LoB = radians(LoB)  
    LaA= radians(LaA)  
    LaB = radians(LaB) 
# The "Haversine formula" is used.
    D_Lo = LoB - LoA 
    D_La = LaB - LaA 
    P = sin(D_La / 2)**2 + cos(LaA) * cos(LaB) * sin(D_Lo / 2)**2  
   
    Q = 2 * asin(sqrt(P))   
    # The earth's radius in kilometers.
    R_km = 6371  
# Then we'll compute the outcome.
    return(Q * R_km)

distance_d(df_LL.o_latitute[1],df_LL.d_latitute[1],df_LL.o_longitude[1],df_LL.d_longitude[1])
