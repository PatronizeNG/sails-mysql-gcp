# Sails-MySQL-GCP Adapter <a target="_blank" href="http://www.mysql.com"><img src="http://www.mysql.com/common/logos/powered-by-mysql-125x64.png" alt="Powered by MySQL" title="sails-mysql-gcp: MySQL adapter for Sails and GCP"/></a> <a target="_blank" href="http://www.mysql.com"><img src="https://cloud.google.com/images/social-icon-google-cloud-1200-630.png" alt="Powered by GCP" title="sails-mysql-gcp: MySQL adapter for Sails and GCP"/></a>

MySQL adapter for the Sails framework and Waterline ORM.  Allows you to use MySQL via your models to store and retrieve data.  Also provides a `query()` method for a direct interface to execute raw SQL commands.



## Installation

1 - Install `sails-mysql` from NPM.

```bash
# In your app:
$ npm install sails-mysql
```

2 - Create an `adapters` folder in your `api` folder

3 - Clone `https://github.com/PatronizeNG/sails-mysql-gcp.git` into the `adapters` folder

4 - Remove Git with `rm -rf .git`

4 - Replace your datastore config with this:

```json
default: {
    adapter: "sails-mysql-gcp",
    socketPath: "/cloudsql/<CLOUD_SQL_CONNECTION_NAME>",
    user: "<USER>",
    password: "<PASSWORD>",
    database: "<DATABASE_NAME>",
  },
```

5 - Your app.yaml should look like this:

```yaml
runtime: nodejs
env: flex
service: sails-app
beta_settings:
  # The connection name of your instance, available by using
  # 'gcloud beta sql instances describe [INSTANCE_NAME]' or from
  # the Instance details page in the Google Cloud Platform Console.
  cloud_sql_instances: YOUR_INSTANCE_CONNECTION_NAME
```

> You are good to go

