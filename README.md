# mongodb-challenge

In this repository we will explain how to create the DB for the challenge.

First of all we recommend to download [MongoCompass](https://www.mongodb.com/try/download/compass). As we will use the aggregation framework of this tool to solve all the challenges.

Once you installed MongoDB compass, we have to create our local DB and migrate the info for the challenge. We will do this running these commands. **YOU NEED TO HAVE INSTALLED [DOCKER](https://docs.docker.com/get-docker/)**.

You have to download this [file](https://drive.google.com/file/d/1mpT3uuCvXKvoDGwHDwzWFt5g5ccZDMpS/view?usp=sharing) and execute these commands in the same folder you download the file:

*NOTE: As it is a big file with all the DB info, Google Drive might tell you something like this "Google Drive can't scan this file for viruses." but don't worry the file does not contain anything else apart from the challenge database.*

```sh
# Creates mongodb
docker run -d -p 27017:27017 --name mongodb mongo
# restore info
docker exec -i mongodb sh -c 'mongorestore --archive' < db.dump
```

After that you can connect to Mongo Compass adding this connection string `mongodb://localhost:27017`