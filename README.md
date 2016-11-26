

# API 
## Endpoints
* [Token](#oauth-token)
* [Password](#password)
* [Task](#task) 
* [Timer](#timer)

# Oauth
## Oauth Token
#### Make a HTTP request as a grant client for authorization to the ifishent API.
###### POST: /oauth/authorize

The endpoint expects to receive the following parameters as part of the request.
```javascript
   {
     username: [user name],
     password: [password],
     grant_type: [requested grant type],
     client_id: [id],
     client_secret: [client secret]
   } 
```
The HTTP response message will return 200 or 500. If a status code of 200, the response is:
```javascript
   {
     status: 200,
     access_token: [token],
     refresh_token: [token],
     expires_in: [epoch date]
   } 
```

# Password
## Password reset
#### Make a HTTP request to send a password reset email to a given user.
###### GET: /password/reset

The endpoint expects to receive the following parameters as part of the request.
```javascript
   {
     email: [user email,
   } 
```
The HTTP response message will return 200 or 500. If a status code of 200, the response is:
```javascript
   {
     status: 200,
     data: [The API data response as a string.],
     message: [The API response messasge inidicate what has taken place.],
   } 
```

# Task
## Task GET
#### Make a HTTP request for all tasks related to a given user.
###### GET: /tasks
The HTTP response message will return 200 or 500. If a status code of 200, the response is:
```javascript
   {
     data: [
        {
            name: Pick up coffee on the way home
            id: 1234567
            due_date: '11/12/2016'
            time_estimate: '1:20'
            status: 'unstarted'
        }
     ],   
     status: 200,
     message: 'success',
   } 
```

## Task POST
#### Make a HTTP request for to save a task.
###### POST: /tasks

The endpoint expects to receive the following parameters as part of the request.
```javascript
   {
     name: 'Get soy-milk for the cofee.',
     due_date: [nullable]
     time_estimate: [nullable]
   } 
```

The HTTP response message will return 200 or 500. If a status code of 200, the response is:
```javascript
   {
     data: [
        {
            name: 'Get soy-milk for the coffee.'
            id: 1234567
            user_id: 987654321
            due_date: '11/12/2016'
            time_estimate: '1:20'
            status: 'unstarted'
        }
     ],   
     status: 200,
     message: 'success',
   } 
```


## Task PUT
#### Make a HTTP request to update a given task.
###### PUT: /tasks

The endpoint expects to receive the following parameters as part of the request.
```javascript
   {
     id: 1234567
     name: 'Get soy for the coffee and tea'
   } 
```

The HTTP response message will return 200 or 500. If a status code of 200, the response is:
```javascript
   {
     data: [
        {
            name: 'Get soy-milk for the coffee and tea'
            id: 1234567
            user_id: 987654321
            due_date: '11/12/2016'
            time_estimate: '1:20'
            status: 'unstarted'
        }
     ],   
     status: 200,
     message: 'success',
   } 
```

## Task DELETE
#### Make a HTTP request to delete a given task.
###### PUT: /tasks

The endpoint expects to receive the following parameters as part of the request.
```javascript
   {
     id: 1234567
   } 
```

The HTTP response message will return 200 or 500. If a status code of 200, the response is:
```javascript
   {
     description: 'The task that was provided was deleted.',
     status: 200,
     message: 'Task deleted.'
   } 
```


# Timer
## Timer GET
#### Make a HTTP request for a timer.
###### GET: /timers
The HTTP response message will return 200 or 500. If a status code of 200, the response is:
```javascript
   {
     data: [
        {
            id: 1234567
            user_id: 987654321
            expiry: [data/time]
            pause: [boolean]
        }
     ],   
     status: 200,
     message: 'success',
   } 
```

## Timer POST
#### Make a HTTP request for to save a timer.
###### POST: /timer

The endpoint does not expect to any parameters to start a new timer.

The HTTP response message will return 200 or 500. If a status code of 200, the response is:
```javascript
   {
    data: [
        {
            id: 1234567
            user_id: 987654321
            expiry: [data/time]
            pause: [boolean]
        }
     ], 
     status: 200,
     message: 'success',
   } 
```


## Timer PUT
#### Make a HTTP request to update a given timer.
###### PUT: /timer

The endpoint expects to receive the following parameters as part of the request.
```javascript
   {
     id: 1234567
   } 
```

The HTTP response message will return 200 or 500. If a status code of 200, the response is:
```javascript
   {
    data: [
        {
            id: 1234567
            user_id: 987654321
            expiry: [data/time]
            pause: [boolean]
        }
     ], 
     status: 200,
     message: 'success',
   } 
```

## Timer DELETE
#### Make a HTTP request to delete a given task.
###### PUT: /tasks

The endpoint expects to receive the following parameters as part of the request.
```javascript
   {
     id: 1234567
   } 
```

The HTTP response message will return 200 or 500. If a status code of 200, the response is:
```javascript
   {
     description: 'The timer was deleted.',
     status: 200,
     message: 'Task deleted.'
   } 
```