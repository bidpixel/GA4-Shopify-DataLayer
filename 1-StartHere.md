# GA4 Shopify DataLayer Server Side Setup Instructions



## Step 1 - Container Creation
- Create a new web container in GTM, note the container ID (GTM-XXXXXXXX)
- Create a new server container in GTM, selet Manually provision tagging server and note the container config code
- Create a new container in Stape.io https://app.stape.io/container/new
- Add a subdomain (xxx.yourdomain.com) in Stape.io and update your DNS records accordingly
- Enable Custom Loader in stape and add your GTM web container ID, note down the two new GTM code blocks


## Step 2 - Add DataLayer Code to Shopify
- Follow the instructions at to add the datalayer code to Shopify https://github.com/bidpixel/GA4-Shopify-DataLayer/blob/main/DataLayerInstructions.md
- Ensure you use the two GTM code blocks from the previous step


## Step 3 - GTM Server Containers Import & Config
- Import BidPixelServerContainer.json [https://github.com/bidpixel/GA4-Shopify-DataLayer-Server-Side/blob/main/ServerContainer.json](https://github.com/bidpixel/GA4-Shopify-DataLayer-Server-Side/blob/main/BidPixelServerContainer.json)
- Update the "C -" variables
- Admin > Container Settings > Add your server URL (xxx.yourdomain.com) 


## Step 4 - GTM Web Containers Import & Config
- Import WebContainer.json https://github.com/bidpixel/GA4-Shopify-DataLayer-Server-Side/blob/main/WebContainer.json
- Update the "C -" variables


## Step 5 - Test
- Test to check everything is working correctly
