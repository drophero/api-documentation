DropHero API v1 documentation
=============================


Authenticating Requests by Using Query Parameters
-------------------------------------------------

Using query parameters to authenticate requests is useful when you want to express a request entirely in a URL. This method is also referred as presigning a URL. Presigned URLs enable you to grant temporary access to your DropHero client resources. **All requests sended to DropHero API must be presigned in order to control the access and propper data consumption.**

The following is an example presigned URL. 

```
https://api.drophero.com/v1/subscribed
?DHSAccessKeyId=XXXXXXXXX
&Expires=1382116367
&Signature=YzY5NDgwYWE2ZWJhNmRjNjU1MDQxMGViY2Q2ZjBjMjYyMmYwYTk2Mw==
```

Presigning requests
--------------------

In order to access any funtionality provided by DropHero you must be able to presign any request. This involves 3 basic parameters embedded in the url: DHSAccessKeyId, Expires and Signature.

- <code>DHSAccessKeyId</code> parm:

Public DropHero key. Identifies the specific Public Key provided to every registered user.

- <code>Expires</code> parm:

Provides the current time, in seconds from epoch, indicating the time when this request has been signed from the requester. For example, 1382116367. This value is an integer. This value must be valid and express current time in universal GMT. 

This value will be used in the Signature generation process too.

A presigned URL can be valid for a maximum of 600 seconds.

- <code>Signature</code> parm:

Provides the signature to authenticate your request. This signature must match the signature DropHero calculates, otherwise, DropHero denies the request. For example, <code>YzY5NDgwYWE2ZWJhNmRjNjU1MDQxMGViY2Q2ZjBjMjYyMmYwYTk2Mw==</code>

In order to generate this code you will need you current machine time in universal GMT and a DropHero Secret Key, provided to every registered user.

```
key = base64_encode(hash_hmac('SHA1', $currentGTMtime.$secretKey, $secretKey))
```

##No XML, just JSON

We only support JSON for serialization of data. 

You'll receive a 400 Bad Request response code if you attempt to use a different URL parms or this are bad formatted.


## Handling errors

If DropHero is having trouble, you might see a 500 error. 500 means that the app is entirely down, but you might also see 502 Bad Gateway, 503 Service Unavailable, or 504 Gateway Timeout. It's your responsibility in all of these cases to retry your request later

| Response Code | Description          |
| ------------: | ----------- |
| 200  | OK                   |
| 201  | Created              |
| 304  | Not modified         |
| 400  | Bad request          |
| 401  | Unauthorized         |
| 403  | Forbidden            |
| 404  | Not found            |
| 406  | No acceptable        |
| 500  | Internal error       |


## Rate limiting

You can perform up to 1 request per second period from the same IP address for the same account. If you exceed this limit, you'll get banned from our systems for subsequent requests. 

## API ready for use

| slug                      | Function          |
| ------------------------- | ----------- |
| <code>/v1/subscribed</code>  | [Product subscription management](/sections/subscribed.md)                  |
| <code>/v1/shipping</code>  | [Shipping options management](/sections/subscribed.md)                   |
| <code>/v1/category</code>  | [Category synchronization](/sections/subscribed.md)                   |
| <code>/v1/orders</code>  | [Orders management](/sections/subscribed.md)                   |
| <code>/v1/notify</code>  | [Notification system](/sections/subscribed.md)                   |

## Help us make it better

Please tell us how we can make the API better. If you have a specific feature request or if you found a bug, please use GitHub issues. Fork these docs and send a pull request with improvements.