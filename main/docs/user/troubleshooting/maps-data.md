---
sidebar_position: 2
title:  Maps & Data
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
import AndroidStore from '@site/src/components/buttons/AndroidStore.mdx';
import AppleStore from '@site/src/components/buttons/AppleStore.mdx';
import LinksTelegram from '@site/src/components/_linksTelegram.mdx';
import LinksSocial from '@site/src/components/_linksSocialNetworks.mdx';
import Translate from '@site/src/components/Translate.js';
import InfoIncompleteArticle from '@site/src/components/_infoIncompleteArticle.mdx';

<InfoIncompleteArticle/>

## Maps
### Why does OsmAnd not offer access to Google Maps?

Firstly, OsmAnd is meant to support OpenStreetMap and tries to go that path as far as possible. Secondly, there are licensing issues, so OsmAnd cannot be distributed with Google Maps data.

### Is there a way to have contour lines displayed in feet also, instead of meters?

Unfortunately not. This would require the generation of completely separate contour line data with different geometry and labels. You can obviously generate maps yourself using GDAL and OsmAndMapCreator but that requires technical environment check [Technical Documentation](../../technical/index.md).

### Why long-loading maps for Android 11 and Android 12?

There is a storage access rules in [Android 11-12](https://www.androidauthority.com/android-12-privacy-features-1225859/).

The problem was related to the storing maps of SD cards.
Android 11 and 12 very slow file access performance. 

[Discuss on the Reddit](https://www.reddit.com/r/androiddev/comments/kpn68k/android_11_very_slow_file_access_performance/)

[OsmAnd Github issue 1](https://github.com/osmandapp/OsmAnd/issues/10453)

[OsmAnd Github issue 2](https://github.com/osmandapp/OsmAnd/issues/12046)

It's only possible to fix if you migrate maps from sdcard. We're thinking to provide an alternative solution but as of today you can keep some maps on sdcard and copy them manually via FileManager when you need to use them. Sorry for inconvenience but there is no good solution yet.
If this is your case, please try to Migrate your files to Internal app memory and check how it would work for you. 
[Menu->Settings->OsmAnd settings->Data storage folder](../personal/storage#data-storage-folder-android).


### Create own maps

## Search
### Structured (city &#8594; street &#8594; house) address search doesn't find the house

I tried to search CITY - STREET - HOUSE NUMBER and there was no result. 
>Tip: check the full-text search without the city, it may be in another city.

- **No house**. The house isn’t present or house without numbers on OpenStreetMap. Example [here](https://www.openstreetmap.org/#map=19/33.91937/-118.24357).
- **Street name incorrect**. The street name on the house is incorrectly signed in OpenStreetMap. Check the tag addr: street. The street name must exactly match the street name tag.
- **Problem in** [Nominatim](https://www.openstreetmap.org/#map=19/33.91937/-118.24357). The house is present on the OpenStreetMap, but not found in Nominatim. [How to fix addresses](https://wiki.openstreetmap.org/wiki/Addresses).
- **Perhaps a problem in OsmAnd**. The house is present in Nominatim, so this problem in OsmAnd. You can help us to solve it by studying in more detail. [Technical article](../../technical/algorithms/trace-address-search-issues.md).

## Points of Interest

## Tracks and Points
### How to mark different places on the map
*It looks like duplicated content for Personal Data category*
You can leave notes for future usage in several forms:

-   [Favorites](../personal/favorites.md): they are constant points on the map. You can add a description to every Favorite. To add it, please make a long tap -> tap Add.
-   [Markers](../personal/markers.md): the temporary points with the directions settings. You can see the distance from the selected point or your current location to the Marker and remove it fast. To add it, please make a long tap -> tap Marker.
-   [Waypoints](../personal/tracks.md): the points along your route. You can add a description to this point. To add a waypoint, please make a long tap on the map -> Directions -> rst intermediate waypoint.
-   [Audio/Video notes](../plugins/audio-video-notes.md): these are points with your audio-, video-, and photo files added to the selected point on the map. Please enable the Audio/video notes plugin in OsmAnd menu -> Plugins. To add it, please make a long tap -> Actions -> select the required file to add.
-   [OSM Notes](https://www.facebook.com/watch/?v=673312246195291): your reports on the mistakes in the OpenStreetMap source. Please enable the OSM editing plugin in OsmAnd menu -> Plugins. To add it, please make a long tap -> Actions -> Add OSM note.
-   [POIs](../search/index.md): these are the points of interest from the OSM map source. Please enable the POI overlay in Configure map menu or select a certain category in the
-   [Search](../search/index.md).

