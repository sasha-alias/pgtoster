pgtoster
========

PGToster is a happy path tests runner for Postgresql

### Installation

    python setup.py install

### Usage:

    pgtoster <path> <conn_url>

PGToster scans <path> for files with .sql extension and executes statements from there.

Tests within sql files have to be separated by three dashes following by mandatory "test" keyword and optional extra text:

    --- test foo.bar
    SELECT * FROM foo.bar()

    --- test foo.bar1
    SELECT * FROM foo.bar('baz')

    --- test foo.bar.2
    SELECT * FROM foo.bar('baz', 'quz')

Example:

    pgtoster ./tests/ postgresql://user@localhost:5432/dbname

Example of output:

    ...
    Tests run:
        3 executed
        3 successful
        0 failed
