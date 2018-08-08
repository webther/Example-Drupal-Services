## About
These are the examples to show you how to use the Drupal 7 Services in different languages such as PHP, jQuery, Axios and RxJS.

## How to setup?
Install `Services`, `Services Entity` and `REST Server` modules then go to the page /admin/structure/services to config a new service.
Or you can just import the following service example:
```
$endpoint = new stdClass();
$endpoint->disabled = FALSE; /* Edit this to true to make a default endpoint disabled initially */
$endpoint->api_version = 3;
$endpoint->name = 'api_rest_v1';
$endpoint->server = 'rest_server';
$endpoint->path = 'api/rest/v1';
$endpoint->authentication = array(
  'services' => 'services',
);
$endpoint->server_settings = array(
  'formatters' => array(
    'bencode' => TRUE,
    'json' => TRUE,
    'jsonp' => TRUE,
    'php' => TRUE,
    'xml' => TRUE,
  ),
  'parsers' => array(
    'application/json' => TRUE,
    'application/x-www-form-urlencoded' => TRUE,
    'application/xml' => TRUE,
    'multipart/form-data' => TRUE,
    'text/xml' => TRUE,
  ),
);
$endpoint->resources = array(
  'comment' => array(
    'operations' => array(
      'create' => array(
        'enabled' => '1',
      ),
      'retrieve' => array(
        'enabled' => '1',
      ),
      'update' => array(
        'enabled' => '1',
      ),
      'delete' => array(
        'enabled' => '1',
      ),
      'index' => array(
        'enabled' => '1',
      ),
    ),
    'actions' => array(
      'countAll' => array(
        'enabled' => '1',
      ),
      'countNew' => array(
        'enabled' => '1',
      ),
    ),
  ),
  'entity_comment' => array(
    'operations' => array(
      'create' => array(
        'enabled' => '1',
      ),
      'retrieve' => array(
        'enabled' => '1',
      ),
      'update' => array(
        'enabled' => '1',
      ),
      'delete' => array(
        'enabled' => '1',
      ),
      'index' => array(
        'enabled' => '1',
      ),
    ),
    'actions' => array(
      'countAll' => array(
        'enabled' => '1',
      ),
      'countNew' => array(
        'enabled' => '1',
      ),
    ),
  ),
  'entity_file' => array(
    'operations' => array(
      'retrieve' => array(
        'enabled' => '1',
      ),
      'update' => array(
        'enabled' => '1',
      ),
      'delete' => array(
        'enabled' => '1',
      ),
      'index' => array(
        'enabled' => '1',
      ),
      'create' => array(
        'enabled' => '1',
      ),
    ),
    'actions' => array(
      'create_raw' => array(
        'enabled' => '1',
      ),
    ),
  ),
  'entity_node' => array(
    'operations' => array(
      'create' => array(
        'enabled' => '1',
      ),
      'retrieve' => array(
        'enabled' => '1',
      ),
      'update' => array(
        'enabled' => '1',
      ),
      'delete' => array(
        'enabled' => '1',
      ),
      'index' => array(
        'enabled' => '1',
      ),
    ),
    'relationships' => array(
      'files' => array(
        'enabled' => '1',
      ),
      'comments' => array(
        'enabled' => '1',
      ),
    ),
    'targeted_actions' => array(
      'attach_file' => array(
        'enabled' => '1',
      ),
    ),
  ),
  'entity_taxonomy_term' => array(
    'operations' => array(
      'create' => array(
        'enabled' => '1',
      ),
      'retrieve' => array(
        'enabled' => '1',
      ),
      'update' => array(
        'enabled' => '1',
      ),
      'delete' => array(
        'enabled' => '1',
      ),
      'index' => array(
        'enabled' => '1',
      ),
    ),
    'actions' => array(
      'selectNodes' => array(
        'enabled' => '1',
      ),
    ),
  ),
  'entity_taxonomy_vocabulary' => array(
    'operations' => array(
      'create' => array(
        'enabled' => '1',
      ),
      'retrieve' => array(
        'enabled' => '1',
      ),
      'update' => array(
        'enabled' => '1',
      ),
      'delete' => array(
        'enabled' => '1',
      ),
      'index' => array(
        'enabled' => '1',
      ),
    ),
    'actions' => array(
      'retrieveByMachineName' => array(
        'enabled' => '1',
      ),
      'getTree' => array(
        'enabled' => '1',
      ),
    ),
  ),
  'entity_user' => array(
    'operations' => array(
      'create' => array(
        'enabled' => '1',
      ),
      'retrieve' => array(
        'enabled' => '1',
      ),
      'update' => array(
        'enabled' => '1',
      ),
      'delete' => array(
        'enabled' => '1',
      ),
      'index' => array(
        'enabled' => '1',
      ),
    ),
    'actions' => array(
      'login' => array(
        'enabled' => '1',
      ),
      'logout' => array(
        'enabled' => '1',
      ),
      'token' => array(
        'enabled' => '1',
      ),
      'request_new_password' => array(
        'enabled' => '1',
      ),
      'user_pass_reset' => array(
        'enabled' => '1',
      ),
      'register' => array(
        'enabled' => '1',
      ),
    ),
    'targeted_actions' => array(
      'cancel' => array(
        'enabled' => '1',
      ),
      'password_reset' => array(
        'enabled' => '1',
      ),
      'resend_welcome_email' => array(
        'enabled' => '1',
      ),
    ),
  ),
  'file' => array(
    'operations' => array(
      'create' => array(
        'enabled' => '1',
      ),
      'retrieve' => array(
        'enabled' => '1',
      ),
      'delete' => array(
        'enabled' => '1',
      ),
      'index' => array(
        'enabled' => '1',
      ),
    ),
    'actions' => array(
      'create_raw' => array(
        'enabled' => '1',
      ),
    ),
  ),
  'node' => array(
    'operations' => array(
      'retrieve' => array(
        'enabled' => '1',
      ),
      'create' => array(
        'enabled' => '1',
      ),
      'update' => array(
        'enabled' => '1',
      ),
      'delete' => array(
        'enabled' => '1',
      ),
      'index' => array(
        'enabled' => '1',
      ),
    ),
    'relationships' => array(
      'files' => array(
        'enabled' => '1',
      ),
      'comments' => array(
        'enabled' => '1',
      ),
    ),
    'targeted_actions' => array(
      'attach_file' => array(
        'enabled' => '1',
      ),
    ),
  ),
  'system' => array(
    'actions' => array(
      'connect' => array(
        'enabled' => '1',
      ),
      'get_variable' => array(
        'enabled' => '1',
      ),
      'set_variable' => array(
        'enabled' => '1',
      ),
      'del_variable' => array(
        'enabled' => '1',
      ),
    ),
  ),
  'taxonomy_term' => array(
    'operations' => array(
      'retrieve' => array(
        'enabled' => '1',
      ),
      'create' => array(
        'enabled' => '1',
      ),
      'update' => array(
        'enabled' => '1',
      ),
      'delete' => array(
        'enabled' => '1',
      ),
      'index' => array(
        'enabled' => '1',
      ),
    ),
    'actions' => array(
      'selectNodes' => array(
        'enabled' => '1',
      ),
    ),
  ),
  'taxonomy_vocabulary' => array(
    'operations' => array(
      'retrieve' => array(
        'enabled' => '1',
      ),
      'create' => array(
        'enabled' => '1',
      ),
      'update' => array(
        'enabled' => '1',
      ),
      'delete' => array(
        'enabled' => '1',
      ),
      'index' => array(
        'enabled' => '1',
      ),
    ),
    'actions' => array(
      'retrieveByMachineName' => array(
        'enabled' => '1',
      ),
      'getTree' => array(
        'enabled' => '1',
      ),
    ),
  ),
  'user' => array(
    'operations' => array(
      'retrieve' => array(
        'enabled' => '1',
      ),
      'create' => array(
        'enabled' => '1',
      ),
      'update' => array(
        'enabled' => '1',
      ),
      'delete' => array(
        'enabled' => '1',
      ),
      'index' => array(
        'enabled' => '1',
      ),
    ),
    'actions' => array(
      'login' => array(
        'enabled' => '1',
        'settings' => array(
          'services' => array(
            'resource_api_version' => '1.0',
          ),
        ),
      ),
      'logout' => array(
        'enabled' => '1',
        'settings' => array(
          'services' => array(
            'resource_api_version' => '1.0',
          ),
        ),
      ),
      'token' => array(
        'enabled' => '1',
      ),
      'request_new_password' => array(
        'enabled' => '1',
      ),
      'user_pass_reset' => array(
        'enabled' => '1',
      ),
      'register' => array(
        'enabled' => '1',
      ),
    ),
    'targeted_actions' => array(
      'cancel' => array(
        'enabled' => '1',
      ),
      'password_reset' => array(
        'enabled' => '1',
      ),
      'resend_welcome_email' => array(
        'enabled' => '1',
      ),
    ),
  ),
);
$endpoint->debug = 1;
```

Install `CORS` module then got to page /admin/config/services/cors to update the following configuration.
```
api/*|<mirror>|POST,PUT,PATCH,GET,DELETE|Authentication,Accept,Content-Type,X-CSRF-TOKEN|true
```

Config the proper permissions for each role at page /admin/people/permissions.

## Examples
* PHP
* jQuery
* Axios
* RxJS