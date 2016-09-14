Dinkly Uptime Responder Plugin v1.00
====================================

This little plugin exists only as an endpoint for uptime monitoring. In addition to confirming Apache is running
and the site is returning a 200 OK, this also confirms that MySQL is running by connecting to the database and 
writing to a log. By default, it will respond with json indicating the disposition of the response.


Installation
------------

  1. Move the `uptime_responder` folder into your dinkly project's `plugins` folder

  2. Add the following lines under the `plugins` section of your `config/config.yml` file:

    ```yaml
    uptime_responder:
            apps:
                responder:
                    app_name: UptimeResponder
                    is_plugin: true
                    base_href: /responder
                    enabled: true
                    default_module: response
    ```

  3. Make sure to give it a database to talk to as well. Place these lines under the `databases` section of your `config/config.yml` file and tweak as needed:

    ```
    uptime_responder:
            host: localhost
            user: root
            pass: root
            name: dinkly_app
    ```

  4. Build the models - at the command line: `php tools/gen_models.php -s uptime_responder -p uptime_responder -i`


Usage
-----

Just hit one of the following URLs:

  - `/responder` (outputs json)
  
  - `/responder/response/default/format/xml` (outputs xml)

  - `/responder/response/default/format/string` (outputs simple string)


License
-------

The Dinkly Uptime Responder plugin is open-sourced software licensed under the MIT License.


Contact
-------

  - lewsid@lewsid.com
  - github.com/lewsid
