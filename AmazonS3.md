## Buckets

* Buckets need to now have a proper CORS setting along with the cloudfront distribution ([2014-09-03][1])
  * set this on the bucket CORS: `<AllowedOrigin>*</AllowedOrigin>`
  * In CloudFront -> Distribution -> Behaviors for this origin, use the Forward Headers: Whitelist option and whitelist the 'Origin' header.
  * Wait for CloudFront to update itself (usually 20mins or so)

[1]: http://stackoverflow.com/questions/12358173/correct-s3-cloudfront-cors-configuration