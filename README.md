---
title: "map"
author: "Leonardo Longo"
date: "10 July 2020"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

## Leaflet map
Create a leaflet map object.
```{r, echo=FALSE}
map <- leaflet() %>%
  addTiles() %>%
  )
```

Create a marker in Capo Taormina
```{r}
icon1 <- awesomeIcons(
  icon = 'ios-close',
  iconColor = 'blue',
  library = 'ion',
  markerColor = "red"
)

content <- paste(sep = "<br/>",
                 "<b>Capo Taormina</b>"
)
```

Add the marker to the map and display the map.
```{r}
addAwesomeMarkers(lat = 37.8450, lng = 15.2975,
                    icon = icon1,
                    popup = "Welcome to Taormina!") %>%
  addPopups(lat = 37.8450, lng = 15.2975, content,
            options = popupOptions(closeButton = FALSE)
  )
```
