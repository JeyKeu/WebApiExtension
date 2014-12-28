Web APi Extension
=================

Installation
------------

This extension requires:

* Behat 3.0+
* PHP 5.4+

Through Composer
~~~~~~~~~~~~~~~~

The easiest way to keep your suite updated is to use `Composer <http://getcomposer.org>`_:

1. Define dependencies in your ``composer.json``:

    .. code-block:: js

        {
            "require-dev": {
                ...

                "behat/web-api-extension": "~1.0@dev"
            }
        }

2. Install/update your vendors:

    .. code-block:: bash

        $ composer update behat/web-api-extension

3. Activate extension by specifying its class in your ``behat.yml``:

    .. code-block:: yaml

        # behat.yml
        default:
          # ...
          extensions:
            Behat\WebApiExtension: ~

Usage
-----
    .. code-block:: gherkin
        Feature: List All Books
            Given I send a GET request to "/books/"
            Then the response code should be 200
            And the response should countain json:
            """
            [
                {
                    "id":1,
                    "title": "The Aweson Book",
                    "issbn": "ISSBN-nnn",
                    "author": "An Awesome Auther"
                    "edition": "First Edition",
                    "publisher": "An Awesome Publisher"
                }
            ]    
            """"
            
