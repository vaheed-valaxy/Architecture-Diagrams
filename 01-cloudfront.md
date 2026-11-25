<!--
# Cloudfront 
![Cloudfront](diagrams/cloudfront.drawio.svg)  
-->

<div align="center">
  <h1>Cloudfront</h1>
  <img src="diagrams/cloudfront.drawio.svg" alt="cloudfront" width="900"/> 
</div>


1. User request comes to Cloudfront,
2. Request goes to index.html which will inturn go to products page
3. Products page sends request to DynamoDB table to load products
4. DynamoDB Table contains product image URLS(cloudfront based urls), so it returns product urls to products page
4. Cloudfront search for the image in its edge locations if it has a cached image of that, if so cloudfront returns that image
