<!-- markdownlint-disable MD013 -->

# OpenStreetMap Processing and Analysis Toolkit

This repository is intended to provide cross-project OSM dataset consistency
and simplified data provenance archiving by standardizing and centralizing
the processing, versioning, and analysis of OSM datasets.

## Naming Conventions

The following rules are intended to promote cross-project consistency and facilitate archiving:

- Only OSM PBF, and not XML, files are supported as input.
- The OSM version PBF file MUST be in ${osmDir}.
- OSM version names and extract names MUST match the following naming convention.

  - Extract names are lowercase with dashes, followed by the OSM version.

    For example: new-york-210520, albany-county-210520

    "latest" is not an accepted OSM version because it is unsuitable for version tracking.

## Resources

### OpenStreetMap

- [about](https://www.openstreetmap.org/about)
- [wiki](https://wiki.openstreetmap.org/wiki/Main_Page)
- [useful resources](https://labs.mapbox.com/mapping/becoming-a-power-mapper/useful-osm-resources/)
- [Geofabrik region extracts](http://download.geofabrik.de/openstreetmap/)

### Open Source Geospatial Foundation _(OSGeo)_ Geospatial Data Abstraction Library _(GDAL)_

- [Main site](https://www.gdal.org)
- [GitHub](https://github.com/OSGeo/gdal)
- [Configuration file for OSM import](https://github.com/OSGeo/gdal/blob/master/gdal/data/osmconf.ini)

To build a Docker image with OSGeo GDAL with FileGDB support, see
[this](https://github.com/availabs/NYS_RIS_ProcessingAndAnalysis_Toolkit/tree/main/buildOSGeoWitFileGdbSupport/versions/3.2.3/ubuntu_full).

### Osmosis

- [OSM wiki](https://wiki.openstreetmap.org/wiki/Osmosis)
- [github](https://github.com/openstreetmap/osmosis)
  - [releases](https://github.com/openstreetmap/osmosis/releases)

May need to use this to fine tune what is included/excluded in an OSM Version Extract: See
[Data Manipulation Tasks](https://wiki.openstreetmap.org/wiki/Osmosis/Detailed_Usage_0.48#--tag-filter_.28--tf.29)

## Node GDAL-Next

We are using [node-gdal-next](https://github.com/contra/node-gdal-next)
(a fork of [node-gdal](https://github.com/naturalatlas/node-gdal)) because we need
[SQLite and GPKG support](https://github.com/naturalatlas/node-gdal/pull/260#issuecomment-597697047)
