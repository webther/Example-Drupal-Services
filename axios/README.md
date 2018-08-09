## Endpoint
```
var endpoint = 'https://dev-npmjs-drupal7.pantheonsite.io/api/rest/v1';
```

## User Token
```
axios({
  method: 'post',
  url: endpoint + '/user/token.json',
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
    var token = data.token;
  })
  .catch(function (error) {

  });
```

## System Connect
```
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
  })
  .catch(function (error) {
    var data = error.response.data;
  });
```

## User Login
```
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
  })
  .catch(function (error) {
    var data = error.response.data;
  });
```

## User Logout
```
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
  })
  .catch(function (error) {
    var data = error.response.data;
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
axios({
  method: 'get',
  url: endpoint + '/entity_user.json',
  responseType: 'json',
  params: params,
  paramsSerializer: function (params) {
    return jQuery.param(params); // Or return qs.stringify(params);.
  },
  headers: {
    'Content-Type': 'application/json',
    'X-CSRF-TOKEN': TOKEN
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
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
axios({
  method: 'post',
  url: endpoint + '/user/register.json',
  responseType: 'json',
  data: data,
  headers: {
    'Content-Type': 'application/json'
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
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
axios({
  method: 'post',
  url: endpoint + '/user.json',
  responseType: 'json',
  data: data,
  headers: {
    'Content-Type': 'application/json',
    'X-CSRF-TOKEN': TOKEN
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
  });
```

## User Retrieve
```
var params = {
  fields: 'uid,name,mail,roles,files,timezone'
};
axios({
  method: 'get',
  url: endpoint + '/entity_user/1.json',
  responseType: 'json',
  params: params,
  paramsSerializer: function (params) {
    return jQuery.param(params); // Or return qs.stringify(params);.
  },
  headers: {
    'Content-Type': 'application/json',
    'X-CSRF-TOKEN': TOKEN
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
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
axios({
  method: 'put',
  url: endpoint + '/user/1.json',
  responseType: 'json',
  data: data,
  headers: {
    'Content-Type': 'application/json',
    'X-CSRF-TOKEN': TOKEN
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
  });
```

## User Delete
```
axios({
  method: 'delete',
  url: endpoint + '/user/1.json',
  responseType: 'json',
  headers: {
    'Content-Type': 'application/json',
    'X-CSRF-TOKEN': TOKEN
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
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
axios({
  method: 'get',
  url: endpoint + '/entity_node.json',
  responseType: 'json',
  params: params,
  paramsSerializer: function (params) {
    return jQuery.param(params); // Or return qs.stringify(params);.
  },
  headers: {
    'Content-Type': 'application/json'
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
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
axios({
  method: 'post',
  url: endpoint + '/node.json',
  responseType: 'json',
  data: data,
  headers: {
    'Content-Type': 'application/json',
    'X-CSRF-TOKEN': TOKEN
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
  });
```

## Node Retrieve
```
var params = {
  fields: 'nid,vid,title,status,body'
};
axios({
  method: 'get',
  url: endpoint + '/entity_node/1.json',
  responseType: 'json',
  params: params,
  paramsSerializer: function (params) {
    return jQuery.param(params); // Or return qs.stringify(params);.
  },
  headers: {
    'Content-Type': 'application/json'
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
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
axios({
  method: 'put',
  url: endpoint + '/node/1.json',
  responseType: 'json',
  data: data,
  headers: {
    'Content-Type': 'application/json',
    'X-CSRF-TOKEN': TOKEN
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
  });
```

## Node Delete
```
axios({
  method: 'delete',
  url: endpoint + '/node/1.json',
  responseType: 'json',
  headers: {
    'Content-Type': 'application/json',
    'X-CSRF-TOKEN': TOKEN
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
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
axios({
  method: 'get',
  url: endpoint + '/entity_file.json',
  responseType: 'json',
  params: params,
  paramsSerializer: function (params) {
    return jQuery.param(params); // Or return qs.stringify(params);.
  },
  headers: {
    'Content-Type': 'application/json'
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
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
axios({
  method: 'post',
  url: endpoint + '/file.json',
  responseType: 'json',
  data: data,
  headers: {
    'Content-Type': 'application/json',
    'X-CSRF-TOKEN': TOKEN
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
  });
```

## File Retrieve
```
var params = {
  fields: 'fid,file,filename,filemime,filesize,status,timestamp,uri,uri_full'
};
axios({
  method: 'get',
  url: endpoint + '/entity_file/1.json',
  responseType: 'json',
  params: params,
  paramsSerializer: function (params) {
    return jQuery.param(params); // Or return qs.stringify(params);.
  },
  headers: {
    'Content-Type': 'application/json'
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
  });
```

## File Update
```
N/A
```

## File Delete
```
axios({
  method: 'delete',
  url: endpoint + '/file/1.json',
  responseType: 'json',
  headers: {
    'Content-Type': 'application/json',
    'X-CSRF-TOKEN': TOKEN
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
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
axios({
  method: 'get',
  url: endpoint + '/entity_taxonomy_vocabulary.json',
  responseType: 'json',
  params: params,
  paramsSerializer: function (params) {
    return jQuery.param(params); // Or return qs.stringify(params);.
  },
  headers: {
    'Content-Type': 'application/json'
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
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
axios({
  method: 'post',
  url: endpoint + '/entity_taxonomy_vocabulary.json',
  responseType: 'json',
  data: data,
  headers: {
    'Content-Type': 'application/json',
    'X-CSRF-TOKEN': TOKEN
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
  });
```

## Taxonomy Vocabulary Retrieve
```
var params = {
  fields: 'vid,name,machine_name,description,hierarchy,module,weight',
};
axios({
  method: 'get',
  url: endpoint + '/entity_taxonomy_vocabulary/1.json',
  responseType: 'json',
  params: params,
  paramsSerializer: function (params) {
    return jQuery.param(params); // Or return qs.stringify(params);.
  },
  headers: {
    'Content-Type': 'application/json'
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
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
axios({
  method: 'put',
  url: endpoint + '/entity_taxonomy_vocabulary/1.json',
  responseType: 'json',
  data: data,
  headers: {
    'Content-Type': 'application/json',
    'X-CSRF-TOKEN': TOKEN
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
  });
```

## Taxonomy Vocabulary Delete
```
var data = {
  vid: 1
};
axios({
  method: 'delete',
  url: endpoint + '/entity_taxonomy_vocabulary/1.json',
  responseType: 'json',
  data: data,
  headers: {
    'Content-Type': 'application/json',
    'X-CSRF-TOKEN': TOKEN
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
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
axios({
  method: 'get',
  url: endpoint + '/entity_taxonomy_term.json',
  responseType: 'json',
  params: params,
  paramsSerializer: function (params) {
    return jQuery.param(params); // Or return qs.stringify(params);.
  },
  headers: {
    'Content-Type': 'application/json'
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
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
axios({
  method: 'post',
  url: endpoint + '/entity_taxonomy_term.json',
  responseType: 'json',
  data: data,
  headers: {
    'Content-Type': 'application/json',
    'X-CSRF-TOKEN': TOKEN
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
  });
```

## Taxonomy Term Retrieve
```
var params = {
  fields: 'vid,tid,name,vocabulary_machine_name,is_new,weight,parent',
};
axios({
  method: 'get',
  url: endpoint + '/entity_taxonomy_term/1.json',
  responseType: 'json',
  params: params,
  paramsSerializer: function (params) {
    return jQuery.param(params); // Or return qs.stringify(params);.
  },
  headers: {
    'Content-Type': 'application/json'
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
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
axios({
  method: 'put',
  url: endpoint + '/entity_taxonomy_term/1.json',
  responseType: 'json',
  data: data,
  headers: {
    'Content-Type': 'application/json',
    'X-CSRF-TOKEN': TOKEN
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
  });
```

## Taxonomy Term Delete
```
var data = {
  vid: 1
};
axios({
  method: 'delete',
  url: endpoint + '/entity_taxonomy_term/1.json',
  responseType: 'json',
  data: data,
  headers: {
    'Content-Type': 'application/json',
    'X-CSRF-TOKEN': TOKEN
  },
  withCredentials: true
})
  .then(function (response) {
    var data = response.data;
  })
  .catch(function (error) {
    var data = error.response.data;
  });
```
