# UsersNPhotos

Design and implement a simple app providing REST API for loading and showing Facebook user’s photos.

The app will be given an access token of a user and will load that user data + data for photos the user has been tagged in, and store all into database.
Another endpoint will allow reading of those data by specifying FB ID of a user and returning photos (if any were loaded). No requests to FB should be done, because no access token will be provided to this GET endpoint.
Second endpoint will be used for removing the user+photos data in case we don’t care for him anymore.
Endpoints should look like this (feel free to customize if something doesn’t seem right):

POST /users - request body containing JSON with user FB ID and access token
DELETE /users/{user_fb_id} - deletes the user and his photos from application DB (don’t delete photos on Facebook)
GET /users/{user_fb_id} - responding with the user details (FB ID, name, gender, profile picture URL)
GET /users/{user_fb_id}/photos - responding with list of photos (each with: URL on FB, URL of image file, album name (if any), numbers of reactions grouped by type); can optionally support sorting too (for example by sum of reactions)
For testing you’ll need a FB app, through which you’ll get an access token. I suggest using FB’s Graph API explorer where you can test your queries and safely approve all necessary permissions. (We’ll probably use explorer’s tokens for testing too.)

Technologies we’d like you to use:
Spring (Boot)
Hibernate - we prefer HQL over Criteria
Git - please create public repo and do regular commits just like this was any other production project
Technologies we wouldn’t like you to use:
hbm2ddl - we write update SQL scripts for each DB change; instead of Hibernate we use Flyway for DB migrations
Few other thoughts:
it’d be great if you write down any ideas and thoughts you have - possible improvements; what worked and what didn’t; basically anything. so we can see that you have developer’s critical thinking :-))
try to design a nice API with nice responses, status codes, etc. think the data loading through and find the best way to use 3rd party API;
3rd party APIs often have unexpected errors - try to expect them :-) don’t get stuck on a minor issue; even partially working app is a result for us and - just like in a real project - is better than nothing
Feel free to ask further questions (you don’t have to include others in CC). We’re sure you know how to write code, but we’d like to see that you can find the best solution or maybe even improvements in the task itself.
