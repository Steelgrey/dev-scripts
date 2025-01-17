Scripts that make local Metabase development handier. Currently, these only consist of scripts for running different
databases we support like MySQL or Spark SQL locally, but we can add scripts for other stuff in the future if we think
of anything good.

Please feel free to collaborate, and improve these scripts or add new ones!

### Database Scripts

These scripts run the same Docker images with the same env vars we use in CI, and then dump out some useful info for
using them. They also nuke the existing image when you run the script a second time, so you can just run it again to
completely reset the DB e.g. when running tests.

```bash
$ ~/mb-scripts/run-mariadb-latest.sh
Removing existing container...
maria-db-latest
Nothing to remove
73003b822d25aaf5b55f739f9b91f94f7f8d16a5abbd43b76fb2d34116d49ceb
Started MariaDB latest on port 3306.

jdbc:mysql://localhost:3306/metabase_test?user=root

MB_DB_TYPE=mysql MB_DB_DBNAME=metabase_test MB_DB_HOST=localhost MB_DB_PASS='' MB_DB_PORT=3306 MB_DB_USER=root MB_MYSQL_TEST_USER=root

mysql --user=root --host=127.0.0.1 --port=3306 --database=metabase_test
```

You need to have Docker installed to use these scripts!
