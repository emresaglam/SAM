# SAM - System Architecture Mapper

SAM is a tool designed to map a network based on the data log of a router.
It runs as a local python-based server and displays the a map and statistics on the browser.

## Prerequisites

MySQL - SAM will support other databases in the future:

    apt-get install mysql-server
    apt-get install libmysqlclient-dev

Python - python-dev is needed to build the MySQLdb package

    apt-get install python
    apt-get install python-dev

Pip - _optional_, but convenient for installing python packages

    apt-get install python-pip

## Installation

1. Clone the repository
2. Run `pip install -r requirements.txt` from within the directory. (Or do so manually--See text file for package names)
3. Duplicate `dbconfig.py` as `dbconfig_local.py` and fill out database credentials
3. Run `setup.py` from command line

## Usage

1. Import log files via `import_paloalto.py`. The paloalto system log format is expected.  Other formats will be supported in the future.

   For example: `python import_paloalto.py data/syslog.txt`

   Repeat this for all your data logs before moving on to the next step.

2. Run the preprocessing script `python preprocess.py` to analyze and organize the data
3. Start the server locally by running: `python server.py`
4. Navigate your browser to localhost:8080 and use your mouse to explore the network map
