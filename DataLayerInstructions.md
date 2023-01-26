Source: https://github.com/TechnicalWebAnalytics/dataLayer-shopify

# Shopify Data Layer

## Definition
A data layer helps you collect more accurate analytics data, that in turn allows you to better understand what potential buyers are doing on your website and where you can make improvements. It also reduces the time to implement marketing tags on a website, and reduces the need for IT involvement, leaving them to get on with implementing new features and fixing bugs.

## Integration Instructions

Keep note that this is a base template that attempts to exploit Shopify’s data rendering capabilities and create an ease of integration for dataLayers that can be reused across all Shopify sites. Nonetheless, each site could carry variations that may not be completely compatible with this template. There may also be some areas of data we may have missed, may be a new configuration, or we wouldn’t know is necessary for your efforts. It is highly recommended to review the entire implementation and make your own configurations if needed.

Please let us know if you have any questions or concerns and we will be happy to follow up as soon as possible :)

There are 2 types of Installations provided below. Review each option and choose **one**.

---

### Installation Option 1: 
If the **Checkout page _cannot be edited_**,  use this option. ( Checkout page edits are only available on Shopify Plus. )

#### Assets
|Assets|Integration Type| Asset Type|
| --------|---------|---------|
|theme.liquid ( or your primary theme template )|Modification|**Layout:** *Online Store > Themes > ... > Edit HTML/CSS > Layout > theme.liquid ( or primary theme template )*|
|confirmation page|Modification|**Admin Setting:** *Settings > Checkout > Order Processing > Additional Pixels & Scripts*|
|dataLayer-allPages|Creation|**Snippet:** *Online Store > Themes > ... > Edit HTML/CSS > Snippets > ( will create Snippet in instructions )*|
|Google Tag Manager or any other Tag Manager Code|Creation or Modification|This can either be a **Snippet** ( unless adding to the confirmation page ) or added directly into your **Layout**|

**GTM / Tag Manager Installation or Modification**
  * Within the **theme.liquid** layout, place the GTM / Tag Manager container ( snippet or actual code block ) **directly below the opening \<body> tag**.
  * Within the **confirmation page** the GTM / Tag Manager container ( actual code block ONLY ) should be placed above all additional scripts. **Important Note:** Snippets cannot be applied to the confirmation page, any scripts MUST be placed as an actual code block.
  
**Create the dataLayer-allPages snippet ( _use exact naming and casing!_ )**
  * Create a snippet called **_dataLayer-allPages_** and copy over the provided *[dataLayer-allPages.js](https://github.com/TechnicalWebAnalytics/dataLayer-shopify/blob/master/dataLayer-allPages.js)* in the newly created snippet. In the code, navigate to the “Dynamic Dependencies” section and make any necessary changes.

```javascript
/**********************
* DYNAMIC DEPENDENCIES
***********************/
        
 __DL__ = {
    dynamicCart: true,  // if cart is dynamic (meaning no refresh on cart add) set to true
    debug: true, // if true, console messages will be displayed
    cart: null,
    wishlist: null,
    removeCart: null
};
        
customBindings = {
    cartTriggers: [],
    viewCart: [],
    removeCartTrigger: [],
    cartVisableSelector: [],
    promoSubscriptionsSelectors: [],
    promoSuccess: [],
    ctaSelectors: [],
    newsletterSelectors: [],
    newsletterSuccess: [],
    searchPage: [],
    wishlistSelector: [],
    removeWishlist: [],
    wishlistPage: [],
    searchTermQuery: [getURLParams('q')], // replace var with correct query
};
        
```

**Add the code to the layouts**
  * Within the **theme.liquid** layout, place this include snippet `{% include 'dataLayer-allPages' %}` right before the closing \</head> tag
  * Within the **confirmation page** admin settings, copy over the provided *[dataLayer-allPages.js](https://github.com/TechnicalWebAnalytics/dataLayer-shopify/blob/master/dataLayer-allPages.js)* code directly above the GTM code block. ( Remember, snippets cannot be used in this section so the actual code block must be added )
  
**Prerequisite Library**
* These are already included in the dataLayer build.
  
**Review, Test, Done :)**
  
---

### Installation Option 2: 
If the **Checkout page _can be edited_**, use this option.

#### Assets
|Assets|Integration Type| Asset Type|
| --------|---------|---------|
|theme.liquid ( or your primary theme template )|Modification|**Layout:** *Online Store > Themes > ... > Edit HTML/CSS > Layout > theme.liquid ( or primary theme template )*|
|checkout.liquid|Modification|**Layout:** *Online Store > Themes > ... > Edit HTML/CSS > Layout > checkout.liquid*|
|dataLayer-allPages|Creation|**Snippet:** *Online Store > Themes > ... > Edit HTML/CSS > Snippets > ( will create Snippet in instructions )*|
|Google Tag Manager or any other Tag Manager Code|Creation or Modification|This can either be a **Snippet** or added directly into your **Layout**|

#### Instructions ( Option 2 )
**GTM / Tag Manager Installation or Modification**
  * Within the **theme.liquid & checkout.liquid** layout, place the GTM / Tag Manager container ( snippet or actual code block ) **directly below the opening \<body> tag**.

**Create the dataLayer-allPages Snippet ( _use exact naming and casing!_ )**
  * Create a snippet called **_dataLayer-allPages_** and copy over the provided *[dataLayer-allPages.js](https://github.com/TechnicalWebAnalytics/dataLayer-shopify/blob/master/dataLayer-allPages.js)* in the newly created snippet. In the code, navigate to the “Dynamic Dependencies” section and make any necessary changes.

  ```javascript
/**********************
* DYNAMIC DEPENDENCIES
***********************/
        
 __DL__ = {
    dynamicCart: true,  // if cart is dynamic (meaning no refresh on cart add) set to true
    debug: true, // if true, console messages will be displayed
    cart: null,
    wishlist: null,
    removeCart: null
};
        
customBindings = {
    cartTriggers: [],
    viewCart: [],
    removeCartTrigger: [],
    cartVisableSelector: [],
    promoSubscriptionsSelectors: [],
    promoSuccess: [],
    ctaSelectors: [],
    newsletterSelectors: [],
    newsletterSuccess: [],
    searchPage: [],
    wishlistSelector: [],
    removeWishlist: [],
    wishlistPage: [],
    searchTermQuery: [getURLParams('q')], // replace var with correct query
};
```


**Add the code to the layouts**
  * Within the **theme.liquid** layout, place this include snippet `{% include 'dataLayer-allPages' %}` right before the closing \</head> tag
  * Within the **checkout.liquid** layout, place this include snippet `{% include 'dataLayer-allPages' %}` right before the closing \</head> tag
  
**Prerequisite Library**
* These are already included in the dataLayer build.
  
5. **Review, Test, Done :)**
