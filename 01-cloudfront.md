<!--
# Cloudfront 
![Cloudfront](diagrams/cloudfront.drawio.svg)  
-->

<div align="center">
  <h1>Cloudfront</h1>
  <img src="diagrams/cloudfront.drawio.svg" alt="cloudfront" width="900"/> 
</div>

1. User request comes to Cloudfront.
2. Request goes to index.html which will inturn go to products page.
3. Products page sends request to DynamoDB table to load products.
4. DynamoDB Table contains product image URLS(cloudfront based urls), so it returns product urls to products page.
5. Product microservice sends image urls to cloudfront.
6. Cloudfront search for the images in its edge locations if it has a cached image of that, if so cloudfront returns that image to end user.
7. If Cloudfront does not have a cached image/content cloudfront will go to its origin(S3/ALB) in our case S3 and get that content as well as cache that content in its edge locations/servers, so the next requests will get the content from edge locations/servers.
8. Response (either from step:6 or step:7) will go to end user.
