## Endpoint
```
var endpoint = 'https://dev-npmjs-drupal7.pantheonsite.io/api/rest/v1';
```

## User Token
```
var userToken$ = Rx.Observable.create((observer) => {
  axios({
    method: 'post',
    url: endpoint + '/user/token.json',
    withCredentials: true
  })
    .then(function (response) {
      var data = response.data;
      var token = data.token;
      observer.next(token);
      observer.complete();
    })
    .catch(function (error) {
      var data = error.response.data;
      observer.error(data);
    });
});

userToken$.subscribe({
  next: (data) => {
    console.log('[data] => ', data);
  },
  error: (data) => {
    console.log('[error] => ', data);
  },
  complete: (data) => {
    console.log('[complete] => ', data);
  },
});
```

## System Connect
```
var systemConnect$ = Rx.Observable.create((observer) => {
  axios({
    method: 'post',
    url: endpoint + '/system/connect.json',
    responseType: 'json',
    headers: {
      'Content-Type': 'application/json',
      'X-CSRF-TOKEN': TOKEN
    },
    withCredentials: true
  })
    .then(function (response) {
      var data = response.data;
      observer.next(data);
      observer.complete();
    })
    .catch(function (error) {
      var data = error.response.data;
      observer.error(data);
    });
});
    
systemConnect$.subscribe({
  next: (data) => {
    console.log('[data] => ', data);
  },
  error: (data) => {
    console.log('[error] => ', data);
  },
  complete: (data) => {
    console.log('[complete] => ', data);
  },
});
```

## User Login
```
var userLogin$ = Rx.Observable.create((observer) => {
  var data = {
    username: 'api',
    password: 'api'
  };
  axios({
    method: 'post',
    url: endpoint + '/user/login.json',
    data: data,
    withCredentials: true
  })
    .then(function (response) {
      var data = response.data;
      observer.next(data);
      observer.complete();
    })
    .catch(function (error) {
      var data = error.response.data;
      observer.error(data);
    });
});

userLogin$.subscribe({
  next: (data) => {
    console.log('[data] => ', data);
  },
  error: (data) => {
    console.log('[error] => ', data);
  },
  complete: (data) => {
    console.log('[complete] => ', data);
  },
});
```

## User Logout
```
var userLogout$ = Rx.Observable.create((observer) => {
  axios({
    method: 'post',
    url: endpoint + '/user/logout.json',
    responseType: 'json',
    headers: {
      'Content-Type': 'application/json',
      'X-CSRF-TOKEN': TOKEN
    },
    withCredentials: true
  })
    .then(function (response) {
      var data = response.data;
      observer.next(data);
      observer.complete();
    })
    .catch(function (error) {
      var data = error.response.data;
      observer.error(data);
    });
});

userLogout$.subscribe({
  next: (data) => {
    console.log('[data] => ', data);
  },
  error: (data) => {
    console.log('[error] => ', data);
  },
  complete: (data) => {
    console.log('[complete] => ', data);
  },
});
```
