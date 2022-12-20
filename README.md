#ecommerce-backend

How to install FLY.IO

*** brew install flyctl

______________________________________________________________________

*** fly launch 

This command detects your Dockerfile and builds it. If you have Docker running locally, it builds it on your machine. If not, it builds it on a Fly build machine. Once your container is built, it's deployed! 

flyctl destroy [APPNAME] [flags]

removes app from fly.io dashboard

*** fly deploy

*** fly open 

opens your deployed app in a browser.

*** flyctl status

Now the application has been deployed, let's find out more about its deployment. This command will provide all essential details.

________________________________________________________________________

For a psql shell, you can just use the fly postgres connect command:

*** flyctl postgres connect -a <postgres-app-name>

You can also forward the server port to your local system with fly proxy:

*** flyctl proxy 5432 -a <postgres-app-name>

Then connect to your Postgres server at localhost:5432. Using psql again, as a trivial example, it would look like this:

*** psql postgres://postgres:<password>@localhost:5432

If you already have something else listening on port 5432, you can run this instead:

*** flyctl proxy 15432:5432 -a <postgres-app-name>

Then connect to localhost:15432.
