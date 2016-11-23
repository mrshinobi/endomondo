Endomondo API
============

Endomondo is not offering oficial app but there is a way how to add/write some data by their mobile API. There not exists documentation and it is very hard to figure out which parameters can be used. Using this is only on your own risk. Endomondo can make changes in this API without any warning.

# Authentication of user
You have to know users email and password. Example:
```
$endomondo = new \Fabulator\Endomondo\Endomondo();
$endomondo->login(USER_EMAIL, USER_PASSWORD);
var_dump($endomondo->getUserInfo());
```

# Get information about existed workouts
You can even export gpx files.
```
$workout = $endomondo->workouts->get('560851703');
$workout->saveGPX('./temp/workout.gpx');
```

# Create workouts
You can easily create workouts. This will create a run in New Year, 35 minutes long and 10.23 km length.

```
$endomondo->workouts->create(\Fabulator\Endomondo\Endomondo::SPORT_RUNNING, new DateTime("2015-01-01 13:45:15"), 35 * 60, 10.23)
```