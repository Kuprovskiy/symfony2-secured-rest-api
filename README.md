Symfony2 Secured REST API
=========================

### Symfony2 Rest Api secured with Json Web Token

[![SensioLabsInsight](https://insight.sensiolabs.com/projects/31052f57-b901-4cdd-bc72-1953c0e1a29c/small.png)](https://insight.sensiolabs.com/projects/31052f57-b901-4cdd-bc72-1953c0e1a29c)

This project is a secured Restful API template for Symfony2 
using [`lexik/LexikJWTAuthenticationBundle`](https://github.com/lexik/LexikJWTAuthenticationBundle)
 [`FriendsOfSymfony/FOSRestBundle`](https://github.com/FriendsOfSymfony/FOSRestBundle) and
 [`FriendsOfSymfony/FOSUserBundle`](https://github.com/FriendsOfSymfony/FOSUserBundle)

Create your REST API in 5 minutes
---------------------------------

1. Clone or fork this repository
        ``` bash
        $ git clone https://github.com/unautreweb/symfony2-secured-rest-api.git
        ```
 
2. Install vendors with [Composer](http://getcomposer.org/):
        ``` bash
        $ composer update
        ```

3. Generate the SSH keys :
   
   ``` bash
   $ openssl genrsa -out app/var/jwt/private.pem -aes256 4096
   $ openssl rsa -pubout -in app/var/jwt/private.pem -out app/var/jwt/public.pem
   ```

4. Configure the SSH keys path in your `config.yml` :
   
   ``` yaml
   lexik_jwt_authentication:
       private_key_path: %kernel.root_dir%/var/jwt/private.pem   # ssh private key path
       public_key_path:  %kernel.root_dir%/var/jwt/public.pem    # ssh public key path
       pass_phrase:      ''                                      # ssh key pass phrase
       token_ttl:        86400                                   # token ttl - defaults to 86400
   ```

Demonstration
------------

Here is an example of the API [rest.unautreweb.net](http://rest.unautreweb.net/v1):

* List of items [http://rest.unautreweb.net/v1/items](http://rest.unautreweb.net/v1/items)
* Show an item [http://rest.unautreweb.net/v1/items/1](http://rest.unautreweb.net/v1/items/1)
* Authentication 
[http://rest.unautreweb.net/v1/user/security/login\_check](http://rest.unautreweb.net/v1/user/security/login\_check) (demo / 123456)


Testing
-------

Setup the test suite using [Composer](http://getcomposer.org/):

    $ composer install --dev

Run it using PHPUnit:

    $ vendor/bin/phpunit


Credits
-------

* Julien Reynaud <hi@unautreweb.com>

License
-------

This project is under the MIT license. See the complete license in the bundle:
 
    LICENSE
