---
title: "Data Sets"
author: "Luis Sarmiento"
format: 
  html: 
    toc: true
    warning: false
    code-fold: true
    code-summary: "Show the Code"
---


This page presents an overall description of the data sets I use to analyze the effect of air pollution on criminality for New York and Mexico City.

Researchers can access the data I use to generate these files in the [dropbox repository](https://www.dropbox.com/sh/1jyjs84sef7t1nt/AABtbantKPm4OyICNEIklpXLa?dl=0)

## Crime data for New York City

The following code-chunk loads into the R-environment the raw crime data for NYC


::: {.cell}

```{.r .cell-code}
# Set the path of the R-studio project
file = "~/Dropbox/DIW/NonLinearCrime/"
# Load the data set (I restrict it to the first observations because of data efficiency)
CrimeNyc = read_rds(paste0(file, "02_GenData/01_crime/CrimesNYC.rds"))
```
:::


We obtain data on NYC criminality from the open data-portal website of New York City. @tbl-CrimesNyc shows the structure of the data. There are 5,995,453 observations. The data set spans from Jan 2006 to Dec 2017. It contains, the crime date, hour, longitude, and latitude, alongside a categorical variable indicating the type of crime. This variable can take the following values: Assault, Burglary, Fraud, Forgery, and Bribery, Larceny, Liberty crimes, Mansloughter, Other, Rape, Robbery, Sex crime, Simple Assault.


::: {#tbl-CrimesNyc .cell .tbl-cap-location-top tbl-cap='Structure of the NYC crime data'}

```{.r .cell-code}
# Show the data set
kbl(head(select(CrimeNyc, date, hour, lat, lon, crime), 3), digits = 2) %>% 
  kable_classic(full_width = T, html_font = "Cambria") %>% 
  kable_styling(bootstrap_option = c("hover")) %>% 
  column_spec(c(1), italic = T, color = "DarkBlue") %>%
  footnote(general = "Sample of the criminality data for New York City. Each observation contains the date, hour, longitude, and latitude of all crimes occuring in the city between 2012 and 2018 alngside a categorical varible indicating the type of crime", general_title = "Notes:", footnote_as_chunk = T)
```

::: {.cell-output-display}
`````{=html}
<table class=" lightable-classic table table-hover" style="font-family: Cambria; margin-left: auto; margin-right: auto; margin-left: auto; margin-right: auto;border-bottom: 0;">
 <thead>
  <tr>
   <th style="text-align:left;"> date </th>
   <th style="text-align:right;"> hour </th>
   <th style="text-align:right;"> lat </th>
   <th style="text-align:right;"> lon </th>
   <th style="text-align:left;"> crime </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> 2011-06-18 </td>
   <td style="text-align:right;"> 21 </td>
   <td style="text-align:right;"> 40.72 </td>
   <td style="text-align:right;"> -73.95 </td>
   <td style="text-align:left;"> Other </td>
  </tr>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> 2011-06-18 </td>
   <td style="text-align:right;"> 21 </td>
   <td style="text-align:right;"> 40.69 </td>
   <td style="text-align:right;"> -73.82 </td>
   <td style="text-align:left;"> Other </td>
  </tr>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> 2011-06-18 </td>
   <td style="text-align:right;"> 21 </td>
   <td style="text-align:right;"> 40.76 </td>
   <td style="text-align:right;"> -73.98 </td>
   <td style="text-align:left;"> Fraud, Forgery, and Bribery </td>
  </tr>
</tbody>
<tfoot><tr><td style="padding: 0; " colspan="100%">
<span style="font-style: italic;">Notes:</span> <sup></sup> Sample of the criminality data for New York City. Each observation contains the date, hour, longitude, and latitude of all crimes occuring in the city between 2012 and 2018 alngside a categorical varible indicating the type of crime</td></tr></tfoot>
</table>

`````
:::

```{.r .cell-code}
# Take away tge data set
rm(CrimeNyc)
```
:::


## Crime data for Mexico City

The following code-chunk loads into the R-environment the crime data for Mexico City


::: {.cell}

:::


The data set for Mexico City spans comes from the open-data portal of the Mexico City Government for the years between 2016 and 2019 and from citizen requests from the observations between 2012 and 2015. @tbl-CrimesCdmx shows the structure of the data. There are 1,563,833 observations. The data set spans from Jan 2012 to Dec 2019. It contains, the crime date, hour, longitude, and latitude, alongside a categorical variable indicating the type of crime. This variable can take the following values: Assault, Burglary, Fraud, Forgery, and Bribery, Homicide, Larceny, Liberty crimes, Mansloughter, Other, Rape, Robbery, Sex crime, Simple Assault.


::: {#tbl-CrimesCdmx .cell .tbl-cap-location-top tbl-cap='Structure of the CDMX crime data'}

```{.r .cell-code}
# Show the data set
kbl(head(select(CrimeCdmx, date, hour, lat, lon, crime), 3), digits = 2) %>% 
  kable_classic(full_width = T, html_font = "Cambria") %>% 
  kable_styling(bootstrap_option = c("hover")) |> 
  column_spec(c(1), italic = T, color = "DarkBlue") %>%
  footnote(general = "Sample of the criminality data for New York City. Each observation contains the date, hour, longitude, and latitude of all crimes occuring in the city between 2012 and 2018 alngside a categorical varible indicating the type of crime", general_title = "Notes:", footnote_as_chunk = T)
```

::: {.cell-output-display}
`````{=html}
<table class=" lightable-classic table table-hover" style="font-family: Cambria; margin-left: auto; margin-right: auto; margin-left: auto; margin-right: auto;border-bottom: 0;">
 <thead>
  <tr>
   <th style="text-align:left;"> date </th>
   <th style="text-align:right;"> hour </th>
   <th style="text-align:right;"> lat </th>
   <th style="text-align:right;"> lon </th>
   <th style="text-align:left;"> crime </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> 2012-01-02 </td>
   <td style="text-align:right;"> 5 </td>
   <td style="text-align:right;"> 19.41 </td>
   <td style="text-align:right;"> -99.13 </td>
   <td style="text-align:left;"> Robbery </td>
  </tr>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> 2012-01-03 </td>
   <td style="text-align:right;"> 15 </td>
   <td style="text-align:right;"> 19.43 </td>
   <td style="text-align:right;"> -99.09 </td>
   <td style="text-align:left;"> Robbery </td>
  </tr>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> 2012-01-01 </td>
   <td style="text-align:right;"> 14 </td>
   <td style="text-align:right;"> 19.39 </td>
   <td style="text-align:right;"> -99.16 </td>
   <td style="text-align:left;"> Robbery </td>
  </tr>
</tbody>
<tfoot><tr><td style="padding: 0; " colspan="100%">
<span style="font-style: italic;">Notes:</span> <sup></sup> Sample of the criminality data for New York City. Each observation contains the date, hour, longitude, and latitude of all crimes occuring in the city between 2012 and 2018 alngside a categorical varible indicating the type of crime</td></tr></tfoot>
</table>

`````
:::

```{.r .cell-code}
# Take away the data set
rm(CrimeCdmx)
```
:::


## Hourly air pollution data for Mexico City

We obtain the hourly data on pollution for Mexico City from the Atmospheric Information Center of the city.


::: {.cell}

```{.r .cell-code}
PolCdmx = read_rds(paste0(file, "02_GenData/02_pol/RawPolCdmx.rds"))
```
:::


The data contains station-level measurements of the key criteria pollutants and weather covariates. In total, it contains 2,673,312 hourly observations divided across 47 measuring stations spanning from Jan 2010 to Dec 2019. @tbl-PolCdmx portrays s sample of the panel with one observation for each station, date, and hour combinations. The file reports the longitude and latitude of the station alongside the concentrations of ozone (o3), fine particulate matter(pm25), coarse particulate matter (pm10), relative humidity (rh), temperature (temp), wind speed (wsp), and wind direction (wdr)


::: {#tbl-PolCdmx .cell .tbl-cap-location-top tbl-cap='Structure of the CDMX pollution data'}

```{.r .cell-code}
# Show the data set
kbl(PolCdmx |> arrange(station, date, hour) |>  
      select(c(station, date, hour, lat, lon, o3, pm25, pm10, rh:wdr)) %>% 
      head(., 5), digits = 2) %>% 
  kable_classic(full_width = T, html_font = "Cambria") %>% 
  kable_styling(bootstrap_option = c("hover")) |> 
  column_spec(c(1), italic = T, color = "DarkBlue") %>%
  footnote(general = "Sample of the air pollution data for Mexico City. Each observation contains the station id ant the date and hour time stamps. It also includes the geo-location of measuring stations and the measures of ozone (o3), fine particulate matter (pm25), coarse particulate matter (pm10), relative humidity (rh), temperature (temp), wind speed (wsp), and wind direction(wdr). Ozone in particles per billion, particulate matters in micrograms per cubic metter, relative humidity in percentage, temperature in celsius, wind speed in knots, and wind direction in meteorological degrees", general_title = "Notes:", footnote_as_chunk = T)
```

::: {.cell-output-display}
`````{=html}
<table class=" lightable-classic table table-hover" style="font-family: Cambria; margin-left: auto; margin-right: auto; margin-left: auto; margin-right: auto;border-bottom: 0;">
 <thead>
  <tr>
   <th style="text-align:left;"> station </th>
   <th style="text-align:left;"> date </th>
   <th style="text-align:right;"> hour </th>
   <th style="text-align:right;"> lat </th>
   <th style="text-align:right;"> lon </th>
   <th style="text-align:right;"> o3 </th>
   <th style="text-align:right;"> pm25 </th>
   <th style="text-align:right;"> pm10 </th>
   <th style="text-align:right;"> rh </th>
   <th style="text-align:right;"> temp </th>
   <th style="text-align:right;"> wsp </th>
   <th style="text-align:right;"> wdr </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> ACO </td>
   <td style="text-align:left;"> 2010-01-01 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 19.64 </td>
   <td style="text-align:right;"> -98.91 </td>
   <td style="text-align:right;"> 11 </td>
   <td style="text-align:right;"> 11 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 74.90 </td>
   <td style="text-align:right;"> 10.13 </td>
   <td style="text-align:right;"> 1.76 </td>
   <td style="text-align:right;"> 347 </td>
  </tr>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> ACO </td>
   <td style="text-align:left;"> 2010-01-01 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 19.64 </td>
   <td style="text-align:right;"> -98.91 </td>
   <td style="text-align:right;"> 15 </td>
   <td style="text-align:right;"> 62 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 56.64 </td>
   <td style="text-align:right;"> 14.49 </td>
   <td style="text-align:right;"> 1.20 </td>
   <td style="text-align:right;"> 357 </td>
  </tr>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> ACO </td>
   <td style="text-align:left;"> 2010-01-01 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 19.64 </td>
   <td style="text-align:right;"> -98.91 </td>
   <td style="text-align:right;"> 20 </td>
   <td style="text-align:right;"> 75 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 57.81 </td>
   <td style="text-align:right;"> 14.08 </td>
   <td style="text-align:right;"> 1.74 </td>
   <td style="text-align:right;"> 348 </td>
  </tr>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> ACO </td>
   <td style="text-align:left;"> 2010-01-01 </td>
   <td style="text-align:right;"> 3 </td>
   <td style="text-align:right;"> 19.64 </td>
   <td style="text-align:right;"> -98.91 </td>
   <td style="text-align:right;"> 29 </td>
   <td style="text-align:right;"> 54 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 54.44 </td>
   <td style="text-align:right;"> 13.97 </td>
   <td style="text-align:right;"> 2.96 </td>
   <td style="text-align:right;"> 332 </td>
  </tr>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> ACO </td>
   <td style="text-align:left;"> 2010-01-01 </td>
   <td style="text-align:right;"> 4 </td>
   <td style="text-align:right;"> 19.64 </td>
   <td style="text-align:right;"> -98.91 </td>
   <td style="text-align:right;"> 29 </td>
   <td style="text-align:right;"> 17 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 52.83 </td>
   <td style="text-align:right;"> 13.59 </td>
   <td style="text-align:right;"> 2.75 </td>
   <td style="text-align:right;"> 349 </td>
  </tr>
</tbody>
<tfoot><tr><td style="padding: 0; " colspan="100%">
<span style="font-style: italic;">Notes:</span> <sup></sup> Sample of the air pollution data for Mexico City. Each observation contains the station id ant the date and hour time stamps. It also includes the geo-location of measuring stations and the measures of ozone (o3), fine particulate matter (pm25), coarse particulate matter (pm10), relative humidity (rh), temperature (temp), wind speed (wsp), and wind direction(wdr). Ozone in particles per billion, particulate matters in micrograms per cubic metter, relative humidity in percentage, temperature in celsius, wind speed in knots, and wind direction in meteorological degrees</td></tr></tfoot>
</table>

`````
:::

```{.r .cell-code}
# Take away the data
rm(PolCdmx)
```
:::


## Hourly air pollution data for New York City

I obtain the hourly pollution data for New York City from the EPA pre-generated data-files.


::: {.cell}

```{.r .cell-code}
PolNyc = read_rds(paste0(file, "02_GenData/02_pol/PolWeatherNYC.rds")) |> ungroup()
```
:::


The data is structured in a pannel format with one observations per station and date-hour combinations. It covers the period from Jan 2000 to Dec 2019 and contains 8,528,826 hourly observations divided across 96 measuring stations. @tbl-PolNyc portrays a sample of the panel whose variables are analogous to @tbl-PolCdmx.


::: {#tbl-PolNyc .cell .tbl-cap-location-top tbl-cap='Structure of the New York City pollution data'}

```{.r .cell-code}
# Show the data set
kbl(PolNyc |> arrange(station, date, hour) |>  
      select(c(station, date, hour, lat, lon, o3, pm25, pm10, rh:wdr)) %>% 
      head(., 5), digits = 2) %>% 
  kable_classic(full_width = T, html_font = "Cambria") %>% 
  kable_styling(bootstrap_option = c("hover")) |> 
  column_spec(c(1), italic = T, color = "DarkBlue") %>%
  footnote(general = "Sample of the air pollution data for New York City. Each observation contains the station id ant the date and hour time stamps. It also includes the geo-location of measuring stations and the measures of ozone (o3), fine particulate matter (pm25), coarse particulate matter (pm10), relative humidity (rh), temperature (temp), wind speed (wsp), and wind direction(wdr). Ozone in particles per billion, particulate matters in micrograms per cubic metter, relative humidity in percentage, temperature in celsius, wind speed in knots, and wind direction in meteorological degrees", general_title = "Notes:", footnote_as_chunk = T)
```

::: {.cell-output-display}
`````{=html}
<table class=" lightable-classic table table-hover" style="font-family: Cambria; margin-left: auto; margin-right: auto; margin-left: auto; margin-right: auto;border-bottom: 0;">
 <thead>
  <tr>
   <th style="text-align:left;"> station </th>
   <th style="text-align:left;"> date </th>
   <th style="text-align:right;"> hour </th>
   <th style="text-align:right;"> lat </th>
   <th style="text-align:right;"> lon </th>
   <th style="text-align:right;"> o3 </th>
   <th style="text-align:right;"> pm25 </th>
   <th style="text-align:right;"> pm10 </th>
   <th style="text-align:right;"> rh </th>
   <th style="text-align:right;"> temp </th>
   <th style="text-align:right;"> wsp </th>
   <th style="text-align:right;"> wdr </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> 000236029 </td>
   <td style="text-align:left;"> 2000-01-01 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 42.99 </td>
   <td style="text-align:right;"> -78.77 </td>
   <td style="text-align:right;"> 15 </td>
   <td style="text-align:right;"> NaN </td>
   <td style="text-align:right;"> NaN </td>
   <td style="text-align:right;"> 72 </td>
   <td style="text-align:right;"> 2.22 </td>
   <td style="text-align:right;"> 3.14 </td>
   <td style="text-align:right;"> 102 </td>
  </tr>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> 000236029 </td>
   <td style="text-align:left;"> 2000-01-01 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 42.99 </td>
   <td style="text-align:right;"> -78.77 </td>
   <td style="text-align:right;"> 16 </td>
   <td style="text-align:right;"> NaN </td>
   <td style="text-align:right;"> NaN </td>
   <td style="text-align:right;"> 67 </td>
   <td style="text-align:right;"> 2.22 </td>
   <td style="text-align:right;"> 3.14 </td>
   <td style="text-align:right;"> 107 </td>
  </tr>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> 000236029 </td>
   <td style="text-align:left;"> 2000-01-01 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 42.99 </td>
   <td style="text-align:right;"> -78.77 </td>
   <td style="text-align:right;"> 14 </td>
   <td style="text-align:right;"> NaN </td>
   <td style="text-align:right;"> NaN </td>
   <td style="text-align:right;"> 68 </td>
   <td style="text-align:right;"> 2.22 </td>
   <td style="text-align:right;"> 3.14 </td>
   <td style="text-align:right;"> 104 </td>
  </tr>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> 000236029 </td>
   <td style="text-align:left;"> 2000-01-01 </td>
   <td style="text-align:right;"> 3 </td>
   <td style="text-align:right;"> 42.99 </td>
   <td style="text-align:right;"> -78.77 </td>
   <td style="text-align:right;"> 9 </td>
   <td style="text-align:right;"> NaN </td>
   <td style="text-align:right;"> NaN </td>
   <td style="text-align:right;"> 74 </td>
   <td style="text-align:right;"> 1.67 </td>
   <td style="text-align:right;"> 3.14 </td>
   <td style="text-align:right;"> 109 </td>
  </tr>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> 000236029 </td>
   <td style="text-align:left;"> 2000-01-01 </td>
   <td style="text-align:right;"> 4 </td>
   <td style="text-align:right;"> 42.99 </td>
   <td style="text-align:right;"> -78.77 </td>
   <td style="text-align:right;"> 10 </td>
   <td style="text-align:right;"> NaN </td>
   <td style="text-align:right;"> NaN </td>
   <td style="text-align:right;"> 77 </td>
   <td style="text-align:right;"> 1.67 </td>
   <td style="text-align:right;"> 3.14 </td>
   <td style="text-align:right;"> 104 </td>
  </tr>
</tbody>
<tfoot><tr><td style="padding: 0; " colspan="100%">
<span style="font-style: italic;">Notes:</span> <sup></sup> Sample of the air pollution data for New York City. Each observation contains the station id ant the date and hour time stamps. It also includes the geo-location of measuring stations and the measures of ozone (o3), fine particulate matter (pm25), coarse particulate matter (pm10), relative humidity (rh), temperature (temp), wind speed (wsp), and wind direction(wdr). Ozone in particles per billion, particulate matters in micrograms per cubic metter, relative humidity in percentage, temperature in celsius, wind speed in knots, and wind direction in meteorological degrees</td></tr></tfoot>
</table>

`````
:::

```{.r .cell-code}
# Take away the data
rm(PolNyc)
```
:::


## Adding values to missing observations with Inverse Distance Weighting

Once I download and clean the hourly pollution data, I fill NAs of stations not measuring specific contaminants with inverse distance weighting. IDW approximates the value of a point in space by weighting the measures of comparable neighbours. The following equation shows the mathematical formula behind the weighting.


$$
\frac{\sum_{i}^{N}\omega(dist_{ij})*pol_{it}}{\sum_{i}^{N}\omega(dist_{ij})} \quad | \quad pol_{it} \rightarrow dist_{ij} = 0 \quad | \quad \Longrightarrow \omega(dist_{ij}) = \frac{1}{distance(x_{i}, x_{j})^p}
$$


In it, $V_{jt}$ is the weighted value at station $j$ at time $t$, $pol_{it}$ is the value of pollution (or weather) at station\~$i$ at time\~$t$, $x_i$ and $x_j$ the geographical coordinates of station $i$ and $j$, and\~$dist_{ij}$ is the distance between stations. The power factor $p$ modifies the weighting load; the greater $p$, the greater the weight of closer stations. We use a weight of two, as recommended by \citet{DeMesnard2013} for air pollution. Furthermore, we cut off stations farther away than twenty kilometres to focus on local variations.


::: {.cell}

```{.r .cell-code}
PolIdw = read_rds(paste0(file, "02_GenData/02_pol/idw.rds"))
```
:::


@tbl-PolIdw shows a sample of the inverse distance weighted data-file.


::: {#tbl-PolIdw .cell .tbl-cap-location-top tbl-cap='Structure of the New York City pollution data'}

```{.r .cell-code}
# Show the data set
kbl(PolIdw |> arrange(station, date, hour) |>  
      select(c(station, date, hour, o3IDW, pm25IDW, pm10IDW)) %>% 
      tail(., 3), digits = 2) %>% 
  kable_classic(full_width = T, html_font = "Cambria") %>% 
  kable_styling(bootstrap_option = c("hover")) |> 
  column_spec(c(1), italic = T, color = "DarkBlue") %>%
  footnote(general = "Sample of the air pollution data for Mexico City and New York. Each observation contains the station id, date, hour, and inverse distance weighted values of ozone (o3), fine particulate matter (pm25), and coarse particulate matter (pm10). Ozone in particles per billion and particulate matters in micrograms per cubic metter", general_title = "Notes:", footnote_as_chunk = T)
```

::: {.cell-output-display}
`````{=html}
<table class=" lightable-classic table table-hover" style="font-family: Cambria; margin-left: auto; margin-right: auto; margin-left: auto; margin-right: auto;border-bottom: 0;">
 <thead>
  <tr>
   <th style="text-align:left;">   </th>
   <th style="text-align:left;"> station </th>
   <th style="text-align:left;"> date </th>
   <th style="text-align:right;"> hour </th>
   <th style="text-align:right;"> o3IDW </th>
   <th style="text-align:right;"> pm25IDW </th>
   <th style="text-align:right;"> pm10IDW </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> 12571198 </td>
   <td style="text-align:left;"> XAL </td>
   <td style="text-align:left;"> 2019-12-31 </td>
   <td style="text-align:right;"> 21 </td>
   <td style="text-align:right;"> 18 </td>
   <td style="text-align:right;"> 18.80 </td>
   <td style="text-align:right;"> 46.04 </td>
  </tr>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> 12571199 </td>
   <td style="text-align:left;"> XAL </td>
   <td style="text-align:left;"> 2019-12-31 </td>
   <td style="text-align:right;"> 22 </td>
   <td style="text-align:right;"> 8 </td>
   <td style="text-align:right;"> 19.89 </td>
   <td style="text-align:right;"> 59.07 </td>
  </tr>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> 12571200 </td>
   <td style="text-align:left;"> XAL </td>
   <td style="text-align:left;"> 2019-12-31 </td>
   <td style="text-align:right;"> 23 </td>
   <td style="text-align:right;"> 8 </td>
   <td style="text-align:right;"> 22.87 </td>
   <td style="text-align:right;"> 56.10 </td>
  </tr>
</tbody>
<tfoot><tr><td style="padding: 0; " colspan="100%">
<span style="font-style: italic;">Notes:</span> <sup></sup> Sample of the air pollution data for Mexico City and New York. Each observation contains the station id, date, hour, and inverse distance weighted values of ozone (o3), fine particulate matter (pm25), and coarse particulate matter (pm10). Ozone in particles per billion and particulate matters in micrograms per cubic metter</td></tr></tfoot>
</table>

`````
:::

```{.r .cell-code}
# Erase the data
rm(PolIdw)
```
:::


## Computing the NowCast Air Quality Index

To obtain a single estimate on the effect of pollution on criminality, I transform the hourly concentration of ozone, coarse particle matter, and fine particulate matter into the now Cast Air Quality Index (NC-AQI). The NC-AQI is an hourly version of the standard air quality index used by the EPA since 1976 to communicate the health consequences of exacerbated air pollution. The idea behind the AQI is to transform the concentration of the main criteria pollutants into an easy-to-understand index value that runs between zero and five hundred units. The NC-AQI is different from the standard AQI because the latter is unsuitable when analysing hourly data as it is only valid in a 24 hours period. The idea of the NC-AQI is to better represent the hourly risks of exposure by weighing nearby hours more heavily than the simple running average used with the standard AQIs. For this, before transforming pollutant concentrations into the AQI, the algorithm transforms the hourly values of of ozone and paticle matters according to equation @eq-nc.


$$ 
  NowCast^i_{st}= \frac{\sum_{t = 1}^{T} w^{t-1} c^i_t}{\sum_{t = 1}^{T} w^{t-1}} \hspace{0.15cm} and  \hspace{0.15cm} w^* = \frac{c_{min}}{c_{max}}
$$ {#eq-nc}


In it, c$^{i}_{st}$ is the observed concentration of pollutant $i$ at station $s$ in time $t$. In cases when a station does not measure one of the three particles used to estimate the index, I use the inverse distance weighted value I estimate in the previous section. $w^*$ is the weighting factor of each observation defined as the ratio of the minimum and maximum concentration value over the specific rolling average; eight hours for $o_3$ and twelve hours for $pm_{10}$ and $pm_{25}$. In cases when the minimum weighting factor for $pm_{10}$ and $pm_{25}$ is lower than 0.5, the algorithm updates it to 0.5. Once I estimate transformed exposure values, I translate them into the AQI with equation @eq-aqi.


$$
AQI^i_{st}= \frac{[NowCast^{i}_{st} - NowCast^{i,min}] - [Aqi^{i, max} - Aqi^{i,min}]}{NowCast^{max} - NowCast^{min}} + Aqi^{min}  
$$ {#eq-aqi}


In it, NowCast$^{i}_{st}$ is the transformed exposure value of pollutant $i$ at time $t$ in station $s$. NowCast$^{i,min}$ and NowCast$^{i,max}$ are the minimum and maximum break values of pollutant $i$ corresponding to each of the five risk categories in which the EPA divides the AQI. Similarly, AQI$_{min}$ and AQI$_{max}$ are the minimum and maximum AQI threshold values for each of these five categories.[^1] At each point in time, the AQI in station $s$ at time $t$ is the highest across all measured contaminants in that station, i.e., $AQI_{st} = max(AQI^i_{st})$.

[^1]: For more information on how to estimate the AQI. I refer the reader to the technical assistance document of the EPA \\citep{Aqi2018}.


::: {.cell}

```{.r .cell-code}
# Load the data
PolNc = read_rds(paste0(file, "02_GenData/02_pol/PolNowCast.rds"))
```
:::


@tbl-PolNc contains a sample of the final data set for air pollution. As with @tab-PolNyc and @tab-PolCdmx, each observation corresponds to a station-date-hour combination. The data contains weather covariates alongside the value of the NowCast AQI, $o_3$, $pm_{10}$, and $pm_{25}$ (as well as their weighted values).


::: {#tbl-PolNc .cell .tbl-cap-location-top tbl-cap='Structure of the New York City pollution data'}

```{.r .cell-code}
# Show the data set
kbl(dplyr::filter(ungroup(PolNc), is.na(NowCast) == F) |> arrange(city, station, date, hour)  |> 
      select(c(city, station, date, hour, NowCast, o3:pm25, o3IDW:pm25IDW, rh:wdr, rain)) %>% 
      head(., 3), digits = 2, row.names = F) %>% 
  kable_classic(full_width = T, html_font = "Cambria") %>% 
  kable_styling(bootstrap_option = c("hover")) |> 
  column_spec(c(1), italic = T, color = "DarkBlue") %>%
  footnote(general = "Sample of the air pollution data for Mexico City and New York. Each observation contains the station id, date, hour, and raw plus inverse distance weighted values of ozone (o3), fine particulate matter (pm25), and coarse particulate matter (pm10). Ozone in particles per billion and particulate matters in micrograms per cubic metter", general_title = "Notes:", footnote_as_chunk = T)
```

::: {.cell-output-display}
`````{=html}
<table class=" lightable-classic table table-hover" style="font-family: Cambria; margin-left: auto; margin-right: auto; margin-left: auto; margin-right: auto;border-bottom: 0;">
 <thead>
  <tr>
   <th style="text-align:left;"> city </th>
   <th style="text-align:left;"> station </th>
   <th style="text-align:left;"> date </th>
   <th style="text-align:right;"> hour </th>
   <th style="text-align:right;"> NowCast </th>
   <th style="text-align:right;"> o3 </th>
   <th style="text-align:right;"> pm10 </th>
   <th style="text-align:right;"> pm25 </th>
   <th style="text-align:right;"> o3IDW </th>
   <th style="text-align:right;"> pm10IDW </th>
   <th style="text-align:right;"> pm25IDW </th>
   <th style="text-align:right;"> rh </th>
   <th style="text-align:right;"> temp </th>
   <th style="text-align:right;"> wsp </th>
   <th style="text-align:right;"> wdr </th>
   <th style="text-align:right;"> rain </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> cdmx </td>
   <td style="text-align:left;"> ACO </td>
   <td style="text-align:left;"> 2010-01-01 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 124 </td>
   <td style="text-align:right;"> 15 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 62 </td>
   <td style="text-align:right;"> 15 </td>
   <td style="text-align:right;"> 151.9 </td>
   <td style="text-align:right;"> 62 </td>
   <td style="text-align:right;"> 56.6 </td>
   <td style="text-align:right;"> 14.5 </td>
   <td style="text-align:right;"> 1.2 </td>
   <td style="text-align:right;"> 357 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> cdmx </td>
   <td style="text-align:left;"> ACO </td>
   <td style="text-align:left;"> 2010-01-01 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 154 </td>
   <td style="text-align:right;"> 20 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 75 </td>
   <td style="text-align:right;"> 20 </td>
   <td style="text-align:right;"> 186.2 </td>
   <td style="text-align:right;"> 75 </td>
   <td style="text-align:right;"> 57.8 </td>
   <td style="text-align:right;"> 14.1 </td>
   <td style="text-align:right;"> 1.7 </td>
   <td style="text-align:right;"> 348 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
  <tr>
   <td style="text-align:left;font-style: italic;color: DarkBlue !important;"> cdmx </td>
   <td style="text-align:left;"> ACO </td>
   <td style="text-align:left;"> 2010-01-01 </td>
   <td style="text-align:right;"> 3 </td>
   <td style="text-align:right;"> 152 </td>
   <td style="text-align:right;"> 29 </td>
   <td style="text-align:right;"> NA </td>
   <td style="text-align:right;"> 54 </td>
   <td style="text-align:right;"> 29 </td>
   <td style="text-align:right;"> 135.4 </td>
   <td style="text-align:right;"> 54 </td>
   <td style="text-align:right;"> 54.4 </td>
   <td style="text-align:right;"> 14.0 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 332 </td>
   <td style="text-align:right;"> 0 </td>
  </tr>
</tbody>
<tfoot><tr><td style="padding: 0; " colspan="100%">
<span style="font-style: italic;">Notes:</span> <sup></sup> Sample of the air pollution data for Mexico City and New York. Each observation contains the station id, date, hour, and raw plus inverse distance weighted values of ozone (o3), fine particulate matter (pm25), and coarse particulate matter (pm10). Ozone in particles per billion and particulate matters in micrograms per cubic metter</td></tr></tfoot>
</table>

`````
:::
:::

