# Age-Pyramid <br><br/>

### Dashboard
<p align="center">
<img width="650em" src="https://github.com/Power-BI-Solutions/Age-Pyramid/blob/main/Age%20Pyramid.gif" align = "center"/>
</p>
<br><br/>

### Data Source
- [United States Census Bureau](https://www.census.gov/data.html)

<br><br/>

### Custom Measures

```dax
% of total pop = 
DIVIDE([Total Pop], [All Ages Total Pop], 0)
``` 

```dax
All Ages Total Pop = 
CALCULATE([Total Pop],
    ALL(dimAgeGroup))
``` 

```dax
Display year = 
IF (
    HASONEVALUE ( dimCensusYear[Year] ),
    FORMAT ( MIN ( dimCensusYear[Year] ), "0000" ),
    FORMAT ( MIN ( dimCensusYear[Year] ), "0000" ) & " - "
        & FORMAT ( MAX ( dimCensusYear[Year] ), "0000" )
)
``` 

```dax
Total Pop = SUM(factPop[Value])
``` 
<br><br/>

### Model

<p align="center">
<img width="650em" src="https://github.com/Power-BI-Solutions/Age-Pyramid/blob/main/age_pyramid_data.png" align = "center"/>
</p>
<br><br/>

### Acknowledgements
Project is a part of [WoW Power BI (Workout Wednesday) Challenge](https://www.workout-wednesday.com/pbi-2021-w17/)
