# ddb map-showcase

API showcase for a map-based search

## Requirements

- Python (2.7.x)
- Python Setuptools
- Python Virtualenv (optional)
- PostgreSQL Server (9.x)
- Postgis (2.x)
- BASH-like Shell env


## Getting started

- create a new postgis-enabled database on your Postgres server
- (optional) transform the GeoJSON file (assets/database.json) to SQL (using GDAL/ogr2ogr)
- import the generated or sample SQL (database-sample.sql) into the new database
- create a python virtual environment
    - virtualenv $venvpath
- $venvpath/bin/pip install \<directory containing this file\>
- edit the $configfile (development.ini/production.ini)
    - change your sqlalchemy.url parameter to match you local DB environment
    - enter your DDB API OAuthkey
    - change logging options
    - change nominatim service url
    - change nominatim service contactadress (email)
- serve your new ddb application via a WSGI server (e.g. apache+mod_wsgi or waitress via pserve script)
    - $venvpath/bin/pserve $configfile

## Documentation

The documentation for this project is served as ReStructered textfiles. They have to be processed by sphinx to get the
HTML rendered version and code documentation from docstrings. Since sphinx is already install as a dependency, you
need to load your virtualenv and call make.

- source $venvpath/bin/activate
- cd docs
- make clean && make html

The resulting documentation is located at: doc/_build/html/index.html

## Links

* [Web Site](https://www.deutsche-digitale-bibliothek.de/)
* [Developer](http://www.webgis.de/)
