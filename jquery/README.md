## Endpoint
```
var endpoint = 'https://dev-npmjs-drupal7.pantheonsite.io/api/rest/v1';
```

## User Token
```
$('#user_token').click(function() {
  $.ajax({
    url: endpoint + '/user/token.json',
    method: 'POST',
    dataType: 'json',
    xhrFields: {
      withCredentials: true
    },
    beforeSend: function(xhr) {
      xhr.setRequestHeader('Content-Type', 'application/json');
    },
    success: function(response){

    },
    error: function(request, status, error) {

    }
  });
});
```

## System Connect
```
$.ajax({
  url: endpoint + '/system/connect.json',
  method: 'POST',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.setRequestHeader('X-CSRF-Token', TOKEN);
  },
  success: function(response){

  },
  error: function(request, status, error) {

  }
});
```

## User Login
```
var data = {
  username: 'api',
  password: 'api'
};
$.ajax({
  url: endpoint + '/user/login.json',
  method: 'POST',
  dataType: 'json',
  data: JSON.stringify(data),
  xhrFields: {
    withCredentials: true
  },
  beforeSend: function (xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
  },
  success: function (response) {

  },
  error: function (request, status, error) {

  }
});
```

## User Logout
```
$.ajax({
  url: endpoint + '/user/logout.json',
  method: 'POST',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.setRequestHeader('X-CSRF-Token', TOKEN);
  },
  success: function(response){
  
  },
  error: function(request, status, error) {

  }
});
```

## User Index
```
var params = {
  parameters: {
    status: 1
  },
  fields: 'uid,name,mail,roles,files,timezone',
  sort: 'name',
  direction: 'ASC',
  page: 0,
  pagesize: 5
};
var paramsStr = jQuery.param(params);
$.ajax({
  url: endpoint + '/entity_user.json' + '?' + paramsStr,
  method: 'GET',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  beforeSend: function(xhr) {

  },
  success: function(response){

  },
  error: function(request, status, error) {

  }
});
```

## User Register
```
var time = (new Date).getTime();
var data = {
  name: 'TEST' + time,
  pass: 'password',
  mail: 'TEST' + time + '@example.com',
  status: true
};
$.ajax({
  url: endpoint + '/user/register.json',
  method: 'POST',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  data: JSON.stringify(data),
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
  },
  success: function(response) {

  },
  error: function(request, status, error) {

  }
});
```

## User Create
```
var time = (new Date).getTime();
var data = {
  name: 'TEST' + time,
  pass: 'password',
  mail: 'TEST' + time + '@example.com',
  status: true
};
$.ajax({
  url: endpoint + '/user.json',
  method: 'POST',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  data: JSON.stringify(data),
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.setRequestHeader('X-CSRF-Token', TOKEN);
  },
  success: function(response) {

  },
  error: function(request, status, error) {

  }
});
```

## User Retrieve
```
var params = {
  fields: 'uid,name,mail,roles,files,timezone'
};
var paramsStr = jQuery.param(params);
$.ajax({
  cache: false,
  url: endpoint + '/entity_user/1.json' + '?' + paramsStr,
  method: 'GET',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.setRequestHeader('X-CSRF-Token', TOKEN);
  },
  success: function(response){

  },
  error: function(request, status, error) {

  }
});
```

## User Update
```
var time = (new Date).getTime();
var data = {
  name: 'TEST' + time,
  pass: 'password',
  mail: 'TEST' + time + '@example.com',
  status: true
};
$.ajax({
  url: endpoint + '/user/1.json',
  method: 'PUT',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  data: JSON.stringify(data),
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.setRequestHeader('X-CSRF-Token', TOKEN);
  },
  success: function(response) {

  },
  error: function(request, status, error) {

  }
});
```

## User Delete
```
$.ajax({
  url: endpoint + '/user/1.json',
  method: 'DELETE',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.setRequestHeader('X-CSRF-Token', TOKEN);
  },
  success: function(response) {

  },
  error: function(request, status, error) {

  }
});
```

## Node Index
```
var params = {
  parameters: {
    type: ['article', 'page'],
    status: 1
  },
  fields: 'nid,vid,title,status,body',
  sort: 'title',
  direction: 'ASC',
  page: 0,
  pagesize: 5
};
var paramsStr = jQuery.param(params);
$.ajax({
  cache: false,
  url: endpoint + '/entity_node.json' + '?' + paramsStr,
  method: 'GET',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
  },
  success: function(response){

  },
  error: function(request, status, error) {

  }
});
```

## Node Create
```
var time = (new Date).getTime();
var data = {
  title: 'Sample page - ' + time,
  body: {
    und: [
      {
        value: 'This is a sample page.',
        format: 'filtered_html'
      }
    ]
  },
  type: 'page',
  language: 'und'
};
$.ajax({
  url: endpoint + '/node.json',
  method: 'POST',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  data: JSON.stringify(data),
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.setRequestHeader('X-CSRF-Token', TOKEN);
  },
  success: function(response) {

  },
  error: function(request, status, error) {

  }
});
```

## Node Retrieve
```
var params = {
  fields: 'nid,vid,title,status,body'
};
var paramsStr = jQuery.param(params);
$.ajax({
  cache: false,
  url: endpoint + '/entity_node/1.json' + '?' + paramsStr,
  method: 'GET',
  dataType: 'json',
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
  },
  success: function(response){

  },
  error: function(request, status, error) {

  }
});
```

## Node Update
```
var time = (new Date).getTime();
var data = {
  title: 'Sample page - ' + time,
  body: {
    und: [
      {
        value: 'This is a sample page.',
        format: 'filtered_html'
      }
    ]
  },
  type: 'page',
  language: 'und'
};
$.ajax({
  url: endpoint + '/node/1.json',
  method: 'PUT',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  data: JSON.stringify(data),
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.setRequestHeader('X-CSRF-Token', TOKEN);
  },
  success: function(response) {

  },
  error: function(request, status, error) {

  }
});
```

## Node Delete
```
$.ajax({
  url: endpoint + '/node/1.json',
  method: 'DELETE',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.setRequestHeader('X-CSRF-Token', TOKEN);
  },
  success: function(response) {

  },
  error: function(request, status, error) {

  }
});
```

## File Index
```
var params = {
  parameters: {
    status: 1
  },
  fields: 'fid,file,filename,filemime,filesize,status,timestamp,uri,uri_full',
  sort: 'fid',
  direction: 'ASC',
  page: 0,
  pagesize: 5
};
var paramsStr = jQuery.param(params);
$.ajax({
  url: endpoint + '/entity_file.json' + '?' + paramsStr,
  method: 'GET',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  beforeSend: function(xhr) {

  },
  success: function(response){

  },
  error: function(request, status, error) {

  }
});
```

## File Create
```
var time = (new Date).getTime();
var fileName = 'Sample file - ' + time;
var data = {
  file: 'ZmFrZQ==',
  filename: fileName,
  filepath: 'public://' + fileName
};
$.ajax({
  url: endpoint + '/file.json',
  method: 'POST',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  data: JSON.stringify(data),
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.setRequestHeader('X-CSRF-Token', TOKEN);
  },
  success: function(response) {

  },
  error: function(request, status, error) {

  }
});
```

## File Retrieve
```
var params = {
  fields: 'fid,file,filename,filemime,filesize,status,timestamp,uri,uri_full'
};
var paramsStr = jQuery.param(params);
$.ajax({
  cache: false,
  url: endpoint + '/entity_file/1.json' + '?' + paramsStr,
  method: 'GET',
  dataType: 'json',
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
  },
  success: function(response){

  },
  error: function(request, status, error) {

  }
});
```

## File Update
```
N/A
```

## File Delete
```
$.ajax({
  url: endpoint + '/file/1.json',
  method: 'DELETE',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.setRequestHeader('X-CSRF-Token', TOKEN);
  },
  success: function(response) {

  },
  error: function(request, status, error) {

  }
});
```

## Taxonomy Vocabulary Index
```
var params = {
  parameters: {
    hierarchy: 0
  },
  fields: 'vid,name,machine_name,description,hierarchy,module,weight',
  sort: 'vid',
  direction: 'ASC',
  page: 0,
  pagesize: 5
};
var paramsStr = jQuery.param(params);
$.ajax({
  url: endpoint + '/entity_taxonomy_vocabulary.json' + '?' + paramsStr,
  method: 'GET',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  beforeSend: function(xhr) {

  },
  success: function(response){

  },
  error: function(request, status, error) {

  }
});
```

## Taxonomy Vocabulary Create
```
var time = (new Date).getTime();
var name = 'Sample vocabulary - ' + time;
var data = {
  name: name,
  machine_name: 'sample_vocabulary_' + time,
  description: 'Sample vocabulary - ' + time
};
$.ajax({
  url: endpoint + '/entity_taxonomy_vocabulary.json',
  method: 'POST',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  data: JSON.stringify(data),
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.setRequestHeader('X-CSRF-Token', TOKEN);
  },
  success: function(response) {

  },
  error: function(request, status, error) {

  }
});
```

## Taxonomy Vocabulary Retrieve
```
var params = {
  fields: 'vid,name,machine_name,description,hierarchy,module,weight',
};
var paramsStr = jQuery.param(params);
$.ajax({
  cache: false,
  url: endpoint + '/entity_taxonomy_vocabulary/1.json' + '?' + paramsStr,
  method: 'GET',
  dataType: 'json',
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
  },
  success: function(response){

  },
  error: function(request, status, error) {

  }
});
```

## Taxonomy Vocabulary Update
```
var time = (new Date).getTime();
var name = 'Sample vocabulary - ' + time;
var data = {
  vid: 1,
  name: name,
  machine_name: 'sample_vocabulary_' + time,
  description: 'Sample vocabulary - ' + time
};
$.ajax({
  url: endpoint + '/entity_taxonomy_vocabulary/1.json',
  method: 'PUT',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  data: JSON.stringify(data),
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.setRequestHeader('X-CSRF-Token', TOKEN);
  },
  success: function(response) {

  },
  error: function(request, status, error) {

  }
});
```

## Taxonomy Vocabulary Delete
```
var data = {
  vid: 1
};
$.ajax({
  url: endpoint + '/entity_taxonomy_vocabulary/1.json',
  method: 'DELETE',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  data: JSON.stringify(data),
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.setRequestHeader('X-CSRF-Token', TOKEN);
  },
  success: function(response) {

  },
  error: function(request, status, error) {

  }
});
```

## Taxonomy Term Index
```
var params = {
  parameters: {
    vid: 1
  },
  fields: 'vid,tid,name,vocabulary_machine_name,is_new,weight,parent',
  sort: 'tid',
  direction: 'ASC',
  page: 0,
  pagesize: 5
};
var paramsStr = jQuery.param(params);
$.ajax({
  url: endpoint + '/entity_taxonomy_term.json' + '?' + paramsStr,
  method: 'GET',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  beforeSend: function(xhr) {

  },
  success: function(response){

  },
  error: function(request, status, error) {

  }
});
```

## Taxonomy Term Create
```
var time = (new Date).getTime();
var name = 'Sample term - ' + time;
var data = {
  vid: 1,
  name: name
};
$.ajax({
  url: endpoint + '/entity_taxonomy_term.json',
  method: 'POST',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  data: JSON.stringify(data),
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.setRequestHeader('X-CSRF-Token', TOKEN);
  },
  success: function(response) {

  },
  error: function(request, status, error) {

  }
});
```

## Taxonomy Term Retrieve
```
var params = {
  fields: 'vid,tid,name,vocabulary_machine_name,is_new,weight,parent',
};
var paramsStr = jQuery.param(params);
$.ajax({
  cache: false,
  url: endpoint + '/entity_taxonomy_term/1.json' + '?' + paramsStr,
  method: 'GET',
  dataType: 'json',
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
  },
  success: function(response){

  },
  error: function(request, status, error) {

  }
});
```

## Taxonomy Term Update
```
var time = (new Date).getTime();
var name = 'Sample term - ' + time;
var data = {
  vid: 1,
  tid: 1,
  name: name
};
$.ajax({
  url: endpoint + '/entity_taxonomy_term/1.json',
  method: 'PUT',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  data: JSON.stringify(data),
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.setRequestHeader('X-CSRF-Token', TOKEN);
  },
  success: function(response) {

  },
  error: function(request, status, error) {

  }
});
```

## Taxonomy Term Delete
```
var data = {
  tid: 1
};
$.ajax({
  url: endpoint + '/entity_taxonomy_term/1.json',
  method: 'DELETE',
  dataType: 'json',
  xhrFields: {
    withCredentials: true
  },
  data: JSON.stringify(data),
  beforeSend: function(xhr) {
    xhr.setRequestHeader('Content-Type', 'application/json');
    xhr.setRequestHeader('X-CSRF-Token', TOKEN);
  },
  success: function(response) {

  },
  error: function(request, status, error) {

  }
});
```
