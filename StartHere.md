# GA4 Shopify DataLayer Server Side Setup Instructions



## Step 1 - Container Creation
- Create a new web container in GTM, note the container ID (GTM-XXXXXXXX)
- Create a new server container in GTM, selet Manually provision tagging server and note the container config code
- Create a new container in Stape.io https://app.stape.io/container/new
- Add a subdomain in Stape.io and update your DNS records accordingly
- Enable Custom Loader in stape and add your GTM web container ID, note down the two new GTM code blocks


## Step 2 - Add DataLayer Code to Shopify
- Follow the instructions at https://github.com/bidpixel/GA4-Shopify-DataLayer/blob/main/DataLayerInstructions.md
- Ensure you use the two code blocks from the previous step


## Step 3 - GTM Container Import & Config
- 


