# Confluence Docker image

An image with Atlassian Confluence v5.5.6. BYO database.

## Database connection

The connection to the database can be specified with an URL of the format:
```
[database type]://[username]:[password]@[host]:[port]/[database name]
```
Where ```database type``` is either ```mysql``` or ```postgresql``` and the full URL might look like this:
```
mysql://confluence:jellyfish@172.17.0.2/public
```

When a database url is specified Confluence will skip the database configuration step in the setup.

## Configuration

Configuration options are set by setting environment variables when running the image. What follows it a table of the supported variables:

- CONTEXT_PATH

  Context path of the confluence webapp. You can set this to add a path prefix to the url used to access the webapp. i.e. setting this to ```confluence``` will change the url to http://localhost:8080/confluence/. The value ```ROOT``` is reserved to mean that you don't want a context path prefix. Defaults to ```ROOT```

- DATABASE_URL

  Connection URL specifying where and how to connect to a database dedicated to confluence. This variable is optional and if specified will cause the Confluence setup wizard to skip the database setup set.