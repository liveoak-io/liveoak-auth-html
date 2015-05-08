LiveOak auth example
====================
This example demonstrates some basic functionality related to authentication to LiveOak. Authentication is provided by [Keycloak](http://www.keycloak.org) project.
This example is simple Javascript application, which you can use to login into Keycloak and obtain OAuth access token in JWT format from Keycloak. You can also try to send ajax request to 'storage' resource with access token attached in Authorization header.
Storage request will be successful just in case that you are authenticated.

Installing the application
--------------------------

There are two ways that this example may be installed.

### Admin Console:

1. Click "Install Example Application" button, or "Try example applications" link from "Applications" page if you already have applications installed.
2. Click the "Auth" example and then click "Install".

### Manually:

Assumption is that:
* $LIVEOAK points to the directory with your LiveOak server
* $LIVEOAK_EXAMPLES points to the directory with LiveOak examples

Copy the example into the _apps_ directory of your LiveOak server and start the server
```shell
$ cp -r $LIVEOAK_EXAMPLES/auth/auth-html $LIVEOAK/apps
$ sh $LIVEOAK/bin/standalone.sh
````

> An Application Client was created upon installation of the application. Note that the redirect and web origin
> urls are set to 'http://localhost:8080'. If LiveOak is installed at something other than 'http://localhost:8080',
> then it will need to be edited within the Admin Console.

> When installed on OpenShift, be sure to change 'http' to 'https' for the urls mentioned above.

Running the application
-----------------------
* Open your browser and go to http://localhost:8080/auth-html . Now you should see the application with anonymous page

* After click to "login", you will be redirected to Keycloak login screen. Now you can register as some user or login if you already register user before.

* After successful login/registration you will be redirected back to application. You will see details about your access token, details about your profile and your roles.
You can click to "Invoke Storage", which will send ajax request to http://localhost:8080/auth-html/storage with usage of LiveOak javascript SDK.
If you are not authenticated, you will see 401 error. In other case, you will see content of storage resource.
