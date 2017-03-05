CheerMeApp Demo
===============

Installation
------------

Assumptions:

* Elasticsearch is running locally (localhost:9200)
* Tested on Elasticsearch 1.* (the mapping doesn't work on Elasticsearch 2.*)
* Tested on Python 3.4
* Use virtualenv to install Python dependencies

Create basic database (use data from `data/beers.data`)::

    make index

Run backend service::

    make backend

Run frontend service::

    make frontend

Point your browser to::

    http://localhost:8000

and search for a beer.

Known Limitations
-----------------

- After creating/deleting new items, the item list occasionally
  doesn't refresh correctly.
- When the search bar is emptied, previous results are not cleared
  until a new search is issued.
- No functionality to edit items yet.
- No functionality to insert/edit/delete styles/categories yet.
- UI: should ask "Are you very very sure?" before deleting items.
- No caching (each keystroke is an Elasticsearch query) yet.
- No pagination yet.
- Elasticsearch 2.* is not yet supported

License
-------

The textual data in data/* have been retrieved from the producers' 
websites in August 2015.

The code is under MIT license, see LICENSE.


