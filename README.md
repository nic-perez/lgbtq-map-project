[README_2.md](https://github.com/user-attachments/files/27637362/README_2.md)
# Queer Geographies of New York City (1970s–1990s)

## Overview
This project maps the physical spaces that made LGBTQ community life 
possible in New York City across three defining decades: the 1970s, 1980s, 
and 1990s. Bars, ballrooms, community centers, and performance venues are 
plotted on an interactive map drawn from the NYC LGBT Historic Sites Project 
database. Each marker is a placeof refuge for queer people during this era.

## Why This Matters
Most of these spaces no longer exist. Many closed during the AIDS crisis. 
Others were lost to gentrification, or redevelopment. This map 
is a small act of recovery, making visible what has largely been made 
invisible due to time and circumstance.

## The Three Decades
The 1970s were defined by the aftermath of Stonewall and the explosive 
growth of gay liberation organizing. The 1980s were shaped entirely by AIDS,
meaning that the community spaces most prominent were memorials and sites of mourning,
rather than nightclubs.
By the 1990s, the community was both depleted 
and radicalized, and the spaces that remained carried the weight of everyone 
who had passed.


## Workflow
The pipeline moves through eight steps:
**Data**: A JSON file of hundreds of site records is loaded from the NYC LGBT Historic Sites Project. Before any processing begins, the filters are defined upfront: three target decades, a set of allowed venue types, and a requirement for valid coordinates.
**Filtering**: Every record runs a series of checks. Wrong era, wrong type, or missing coordinates will cause it to be skipped. What passes goes into a clean list called results.
**Design**: Each marker gets a decade-specific color and a popup assembled from the site's name, address, era, image, and a link to its full history.
**Map construction**: Folium builds the base map centered on Manhattan. Three separate marker cluster layers sit on top of it, one per decade, which is what makes decade toggling possible. Each layer can be switched on or off independently.
**Output**: A layer control panel lets users filter by decade. A color-coded legend is injected as a fixed HTML overlay. The finished map saves as lgbtq_nyc_map.html.

The **goal**: To make visible what time and circumstance have largely erased, placing markers where communities once gathered so those spaces are not simply forgotten.

## Data Source
Data is drawn from the NYC LGBT Historic Sites Project 
(nyclgbtsites.org, downloaded May 2026). Sites are filtered to 
community-facing locations only i.e.: bars, clubs, ballrooms, community 
organizations, and performance venues. Areas such as residences and cruising 
spots were retracted to focus on spaces of collective life.

## How to Use the Map
Use the decade toggle in the top right corner to filter by era. 
Click any marker to read about the site and follow the link to its 
full history on the NYC LGBT Historic Sites Project. Marker colors 
indicate site type: red for bars and clubs, orange for community 
organizations, and pink for performance venues.

## Files
| File | Description |
|------|-------------|
| `nicoleperezpchfinal(2).ipynb` | Full code for Jupyter |
| `sites.json` | Source data downloaded from nyclgbtsites.org |
| `lgbtq_map.html` | The rendered interactive map |
