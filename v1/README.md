DropHero API v1 documentation
=============================


Authenticating Requests by Using Query Parameters
-------------------------------------------------

Using query parameters to authenticate requests is useful when you want to express a request entirely in a URL. This method is also referred as presigning a URL. Presigned URLs enable you to grant temporary access to your DropHero client resources. **All requests send to DropHero API must be presigned in order to control access.**

The following is an example presigned URL. 

<code>
https://<span></span>api.drophero.com/v1/subscribed<br />
?DHSAccessKeyId=XXXXXXXXX<br />
&Expires=1382116367<br />
&Signature=YzY5NDgwYWE2ZWJhNmRjNjU1MDQxMGViY2Q2ZjBjMjYyMmYwYTk2Mw==
</code>
