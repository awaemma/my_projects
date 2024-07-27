# PG DATA INGESTION
In this part of the project, I explored the use of docker and docker-compose to spin up a postgres infrastructure that would hold all of the olist files from Kaggle(`https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce`). Below were the steps taken to conclude this part:

- First I created the `pg_data_ingestion` folder which would hold all of the files required for this part of the project.
- As a prerequisite, all of the packages in the `requirements.txt` file within the root directory `MY_PROJECTS` needs to be installed to ensure proper running of our codes.
- The `data` folder was created to hold all of the olist data as mentioned ealier, which would be inserted into a postgres table.
- The  `infra_setup` folder holds the `init.sql` file that defines the schema, table structure and a command to copy the files from the `data` folder into the postgres table created.
- The `docker-compose.yml` file describes the services that would be spun up when it is run. In this case, we only have the `postgres` service with the appropriate mapping of the volumes and the entrypoint.


## TO RUN THIS PART 1 OF THE PROJECT
- Start by installing all the requirements in the `requirement.txt` file using `pip install requirement.txt`. You may choose to do this within a python virtual envinroment that you want to use for this project.
- Optionally, you can use any data of your choice, however ensure that the table structure is properly specified in the `init.sql` file within the `infra_setup` folder. Otherwise, use the olist data already provided.
- Run the `docker-compose.yml` file using `docker-compose up` within the `pg_data_ingestion` . Note that the default port for postgres is *`5432`* however, the port has been changed to *`5434`* on the localhost so we avoid any conflict incase you already have a service running on the default port. This step would automatically create a database, schema, tables and load the data as specified in the `init.sql` file.
- Optionally, you can access postgres DB using a client( DBeaver or PG4admin) or through the command line interface.
