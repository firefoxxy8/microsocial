Usage
=====

First create stackExchange app then send request to authorize app.StackExchange redirects the user back to your website's URL after granting access (giving proper permissions) to your application. We call that url **RETURN URL**.

.. code-block:: python

    from stackoverflow import stackoverflow.py

    API_KEY = "your app ID"
    API_SECRET = "your app secret"
    APP_KEY="your app key"
    RETURN_URL = "redirect url"
    authentication=stackoverflow(API_KEY, API_SECRET,APP_KEY,RETURN_URL)
    url=authentication.authorize()
    print authentication_url
    

When you grant access to the application, you will be redirected to the return url with the following query strings appended to your **RETURN_URL**:

.. code-block:: python

    "RETURN_URL/?code=AQTXrv3Pe1iWS0EQvLg0NJA8ju_XuiadXACqHennhWih7iRyDSzAm5jaf3R7I8&state=ea34a04b91c72863c82878d2b8f1836c"


This means that the value of the **authorization_code** is **AQTXrv3Pe1iWS0EQvLg0NJA8ju_XuiadXACqHennhWih7iRyDSzAm5jaf3R7I8**. After setting it by hand, we can call the **.get_access_token()** to get the actual token.

.. code-block:: python

    access_token=authentication.get_accesstoken_from_code("AQTXrv3Pe1iWS0EQvLg0NJA8ju_XuiadXACqHennhWih7iRyDSzAm5jaf3R7I8")
    print access_token
    

Get userinfo
-------------------------------------------

.. code-block:: python
  
    userinfo=authentication.get_userinfo()
    print userinfo
    
    
