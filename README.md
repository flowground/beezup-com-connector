# ![LOGO](logo.png) BeezUP **flow**ground Connector

## Description

A generated **flow**ground connector for the BeezUP API (version 2.0).

Generated from: https://api.apis.guru/v2/specs/beezup.com/2.0/swagger.json<br/>
Generated at: 2019-05-07T17:39:39+03:00

## API Description

# The REST API of BeezUP system
## Overview
The REST APIs provide programmatic access to read and write BeezUP data. 
Basically, with this API you will be able to do everything like you were with your browser on https://go.beezup.com !

The main features are:
- Register and manage your account
- Create and manage and share your stores with your friends/co-workers.
- Import your product catalog and schedule the auto importation
- Search the channels your want to use
- Configure your channels for your catalogs to export your product information:
    - cost and general settings
    - category and columns mappings
    - your will be able to create and manage your custom column
    - put in place exlusion filters based on simple conditions on your product data
    - override product values
    - get product vision for a channel catalog scope
- Analyze and optimize your performance of your catalogs on all yours channels with different type of reportings by day, channel, category and by product.
- Automatize your optimisation by using rules!
- And of course... Manage your orders harvested from all your marketplaces:
    - Synchronize your orders in an uniformized way
    - Get the available actions and update the order status
- ...and more!

## Authentication credentials
The public API with the base path **/v2/public** have been put in place to give you an entry point to our system for the user registration, login and lost password. The public API does not require any credentials.
We give you the some public list of values and public channels for our public commercial web site [www.beezup.com](http://www.beezup.com).

The user API with the base path **/v2/user** requires a token which is available on this page:
https://go.beezup.com/Account/MyAccount

## Things to keep in mind
### API Rate Limits
- The BeezUP REST API is limited to 100 calls/minute.

### Media type
The default media type for requests and responses is application/json. Where noted, some operations support other content types. If no additional content type is mentioned for a specific operation, then the media type is application/json.

### Required content type
The required and default encoding for the request and responses is UTF8.

### Required date time format
All our date time are formatted in ISO 8601 format: 2014-06-24T16:25:00Z.

### Base URL
The Base URL of the BeezUP API Order Management REST API conforms to the following template.

https://api.beezup.com

All URLs returned by the BeezUP API are relative to this base URL, and all requests to the REST API must use this base URL template.

You can test our API on https://api-docs.beezup.com/swagger-ui\
You can contact us on [gitter, #BeezUP/API](https://gitter.im/BeezUP/API)


## Authorization

Supported authorization schemes:
- API Key
## Actions

### Get public channel index

> Use this operation to get the correct link to the channels and to the list of values

*Tags:* `Public - Channels - Public Channels`

#### Input Parameters
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### The channel list for one country

*Tags:* `Public - Channels - Public Channels`

#### Input Parameters
* `countryIsoCode` - _required_ - The country iso code alpha 3 based on this: https://en.wikipedia.org/wiki/ISO_3166-1_alpha-3#Decoding_table \
To know which country are available you have to use the operation: GetChannelsByCountry

* `Accept-Encoding` - _required_ - Allows the client to indicate whether it accepts a compressed encoding to reduce traffic size.
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Get all list names

*Tags:* `Public - List of Values - LOV`

#### Input Parameters
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Get the list of values related to this list name

*Tags:* `Public - List of Values - LOV`

#### Input Parameters
* `listName` - _required_ - The list of value name your want to get
* `Accept-Language` - _optional_ - Indicates that the client accepts the following languages.
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Login

> User Login - The login will give your tokens

*Tags:* `Public - Security - Security`

### Lost password

> Lost password - Your password will be regenerated and sent to your email

*Tags:* `Public - Security - Security`

### User Registration

> User Registration - Create a new user on BeezUP

*Tags:* `Public - Security - Security`

### Get the Analytics API operation index

*Tags:* `Analytics - Global`

### Get the global synchronization status of clicks and orders

> Clicks and orders are eventually consistent. \<br/>
> This operation gets the current global state of projections.

*Tags:* `Analytics - Tracking`

### Get the Analytics API operation index for one store

*Tags:* `Analytics - Global`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Optimise all products

> /!\ WARNING /!\ \<br/>
> Apply the operation on every product related to this request. \<br/>
> This operation is used at the bottom of the analytics page result.

*Tags:* `Analytics - Optimisations`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `actionName` - _required_
    Possible values: reenable, disable.

### Optimise products by category

> /!\ WARNING /!\ \<br/>
> This operation will reenable or disable products's category for every channel indicated in the body.

*Tags:* `Analytics - Optimisations`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `catalogCategoryId` - _required_ - The category identifier concerned by this optimisation
* `actionName` - _required_
    Possible values: reenable, disable.

### Optimise products by channel

> /!\ WARNING /!\ \<br/>
> Apply the operation on every product on this channel.

*Tags:* `Analytics - Optimisations`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `channelId` - _required_ - The channel identifier concerned by this optimisation
* `actionName` - _required_
    Possible values: reenable, disable.

### Optimise product

> /!\ WARNING /!\ \<br/>
> This operation will reenable or disable this product for every channel indicated in the body.

*Tags:* `Analytics - Optimisations`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `productId` - _required_ - The product identifier concerned by this optimisation
* `actionName` - _required_
    Possible values: reenable, disable.

### Copy product optimisations between 2 channels

*Tags:* `Analytics - Optimisations`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Optimise products by page

> /!\ WARNING /!\ \<br/>
> Apply the operation on every product related to this request. \<br/>
> This operation is used at the bottom of the analytics page result.

*Tags:* `Analytics - Optimisations`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `actionName` - _required_
    Possible values: reenable, disable.

### Get the report by category

*Tags:* `Analytics - Statistics`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Get the report by channel

*Tags:* `Analytics - Statistics`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Get the report by day

*Tags:* `Analytics - Statistics`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Get the report by product

*Tags:* `Analytics - Statistics`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Get report filter list for the given store

*Tags:* `Analytics - Reports`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Delete the report filter

*Tags:* `Analytics - Reports`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `reportFilterId` - _required_ - Your report filter identifier

### Get the report filter description

*Tags:* `Analytics - Reports`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `reportFilterId` - _required_ - Your report filter identifier

### Save the report filter

*Tags:* `Analytics - Reports`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `reportFilterId` - _required_ - Your report filter identifier

### Gets the list of rules for a given store

*Tags:* `Analytics - Rules`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Rule creation

*Tags:* `Analytics - Rules`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Get the rules execution history

*Tags:* `Analytics - Rules`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `pageNumber` - _required_ - The page to retrieve
* `pageSize` - _required_ - The count of rule history to retrieve

### Run all rules for this store

*Tags:* `Analytics - Rules`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Delete Rule

*Tags:* `Analytics - Rules`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `ruleId` - _required_ - Your rule identifier

### Gets the rule

*Tags:* `Analytics - Rules`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `ruleId` - _required_ - Your rule identifier

### Update Rule

*Tags:* `Analytics - Rules`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `ruleId` - _required_ - Your rule identifier

### Disable rule

*Tags:* `Analytics - Rules`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `ruleId` - _required_ - Your rule identifier

### Enable rule

*Tags:* `Analytics - Rules`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `ruleId` - _required_ - Your rule identifier

### Move the rule down

*Tags:* `Analytics - Rules`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `ruleId` - _required_ - Your rule identifier

### Move the rule up

*Tags:* `Analytics - Rules`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `ruleId` - _required_ - Your rule identifier

### Run rule

*Tags:* `Analytics - Rules`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `ruleId` - _required_ - Your rule identifier

### Get the latest tracked clicks

*Tags:* `Analytics - Tracking`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `count` - _optional_ - The amount of clicks to retrieve

### Get the latest tracked external orders

*Tags:* `Analytics - Tracking`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `count` - _optional_ - The amount of external orders to retrieve

### Get the latest tracked orders

*Tags:* `Analytics - Tracking`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `count` - _optional_ - The amount of orders to retrieve

### Get the synchronization status of clicks and orders of a store

> Clicks and orders are eventually consistent. \<br/>
> This operation gets the current state of projections for a store.

*Tags:* `Analytics - Tracking`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Get the index of the catalog API

> The operation will give you all the operations you will be able to do and all the LOV used in this API.

*Tags:* `Catalogs - Global`

### Get the BeezUP columns

> Get the BeezUP columns, this columns are used for mapping during the manual catalog importation process.

*Tags:* `Catalogs - Global`

### Get the index of the catalog API for this store

> The operation will give you all the operations you will be able to do on this store for this API.

*Tags:* `Catalogs - Catalog`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Delete Auto Import

*Tags:* `Catalogs - Auto`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Get the auto import configuration

*Tags:* `Catalogs - Auto`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Activate the auto importation of the last successful manual catalog importation.

> Once you have made your fist manual catalog importation with success, you can call this operation to import it automatically. No parameter required, we know which one it is.

*Tags:* `Catalogs - Auto`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Pause Auto Import

*Tags:* `Catalogs - Auto`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Resume Auto Import

*Tags:* `Catalogs - Auto`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Configure Auto Import Interval

*Tags:* `Catalogs - Auto`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Configure Auto Import Schedules

*Tags:* `Catalogs - Auto`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Start Auto Import Manually

*Tags:* `Catalogs - Auto`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Get catalog column list

*Tags:* `Catalogs - Catalog`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Change Catalog Column User Name

*Tags:* `Catalogs - Catalog`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `columnId` - _required_ - The catalog column identifier

### Get category list

*Tags:* `Catalogs - Catalog`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `Accept-Encoding` - _required_ - Indicates that the client accepts that the response will be compressed to reduce traffic size.

### Get custom column list

*Tags:* `Catalogs - Catalog`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Compute the expression for this catalog.

*Tags:* `Catalogs - Catalog`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Delete custom column

*Tags:* `Catalogs - Catalog`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `columnId` - _required_ - The custom column identifier

### Create or replace a custom column

*Tags:* `Catalogs - Catalog`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `columnId` - _required_ - The custom column identifier

### Get the encrypted custom column expression

*Tags:* `Catalogs - Catalog`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `columnId` - _required_ - The custom column identifier

### Change custom column expression

*Tags:* `Catalogs - Catalog`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `columnId` - _required_ - The custom column identifier

### Change Custom Column User Name

*Tags:* `Catalogs - Catalog`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `columnId` - _required_ - The custom column identifier

### Get the latest catalog importation reporting

*Tags:* `Catalogs - Importation Process`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Start Manual Import

*Tags:* `Catalogs - Importation Process`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Get the importation status

*Tags:* `Catalogs - Importation Process`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation

### Cancel importation

*Tags:* `Catalogs - Importation Process`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation

### Get detected catalog columns during this importation.

*Tags:* `Catalogs - Importation Catalog Info`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation

### Configure catalog column

*Tags:* `Catalogs - Importation Catalog Info`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation
* `columnId` - _required_ - The custom column identifier

### Ignore Column

*Tags:* `Catalogs - Importation Catalog Info`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation
* `columnId` - _required_ - The custom column identifier

### Map catalog column to a BeezUP column

*Tags:* `Catalogs - Importation Catalog Info`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation
* `columnId` - _required_ - The catalog column identifier

### Reattend Column

*Tags:* `Catalogs - Importation Catalog Info`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation
* `columnId` - _required_ - The custom column identifier

### Unmap catalog column

*Tags:* `Catalogs - Importation Catalog Info`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation
* `columnId` - _required_ - The catalog column identifier

### Commit Importation

*Tags:* `Catalogs - Importation Process`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation

### Commit columns

*Tags:* `Catalogs - Importation Process`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation

### Configure remaining catalog columns

> This operation should be used after you have mapped the required BeezUP Columns

*Tags:* `Catalogs - Importation Process`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation

### Get custom columns currently place in this importation

*Tags:* `Catalogs - Importation Catalog Info`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation

### Delete Custom Column

*Tags:* `Catalogs - Importation Catalog Info`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation
* `columnId` - _required_ - The custom column identifier

### Create or replace a custom column

*Tags:* `Catalogs - Importation Catalog Info`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation
* `columnId` - _required_ - The custom column identifier

### Get the encrypted custom column expression in this importation

*Tags:* `Catalogs - Importation Catalog Info`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation
* `columnId` - _required_ - The custom column identifier

### Map custom column to a BeezUP column

*Tags:* `Catalogs - Importation Catalog Info`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation
* `columnId` - _required_ - The custom column identifier

### Unmap custom column

*Tags:* `Catalogs - Importation Catalog Info`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation
* `columnId` - _required_ - The custom column identifier

### Get the product sample related to this importation with all columns (catalog and custom)

*Tags:* `Catalogs - Importation Catalog Info`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation
* `productSampleIndex` - _required_ - Index of the product sample. Starting from 0 to 99.

### Get product sample custom column value related to this importation.

> /!\ Use this operation only when you just changed the custom column expression and you want to get a precise the property value. Otherwise use the operation Importation_GetProductSample which will give you all property values

*Tags:* `Catalogs - Importation Catalog Info`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation
* `productSampleIndex` - _required_ - Index of the product sample. Starting from 0 to 99.
* `columnId` - _required_ - The custom column identifier

### Get technical progression

*Tags:* `Catalogs - Importation Process`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `executionId` - _required_ - The execution identifier of you catalog importation

### Get the last input configuration

*Tags:* `Catalogs - Catalog`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Get product by Sku

*Tags:* `Catalogs - Catalog`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `sku` - _required_ - The product sku you want to get

### Get product list

*Tags:* `Catalogs - Catalog`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Get random product list

> We will return 10 products randomly selected with all product values

*Tags:* `Catalogs - Catalog`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Get product by ProductId

*Tags:* `Catalogs - Catalog`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `productId` - _required_ - The product identifier you want to get

### List all your current channel catalogs

*Tags:* `Channel Catalogs - Global`

#### Input Parameters
* `storeId` - _optional_ - The store identifier

### Add a new channel catalog

*Tags:* `Channel Catalogs - Global`

### Get channel catalog exclusion filter operators

*Tags:* `Channel Catalogs - Exclusion Filters`

### Get channel catalog products related to these channel catalogs

*Tags:* `Channel Catalogs - Products`

### Delete the channel catalog

*Tags:* `Channel Catalogs - Global`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier

### Get the channel catalog information

*Tags:* `Channel Catalogs - Global`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier

### Get channel catalog categories

*Tags:* `Channel Catalogs - Categories`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier

### Configure channel catalog category

*Tags:* `Channel Catalogs - Categories`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier

### Disable a channel catalog category mapping

*Tags:* `Channel Catalogs - Categories`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier

### Reenable a channel catalog category mapping

*Tags:* `Channel Catalogs - Categories`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier

### Configure channel catalog column mappings

*Tags:* `Channel Catalogs - Column Mappings`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier

### Disable a channel catalog

*Tags:* `Channel Catalogs - Settings`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier

### Enable a channel catalog

*Tags:* `Channel Catalogs - Settings`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier

### Get channel catalog exclusion filters

*Tags:* `Channel Catalogs - Exclusion Filters`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier

### Configure channel catalog exclusion filters

*Tags:* `Channel Catalogs - Exclusion Filters`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier

### Get the exportation cache information

*Tags:* `Channel Catalogs - Exportations`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier

### Clear the exportation cache

*Tags:* `Channel Catalogs - Exportations`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier

### Get the exportation history

*Tags:* `Channel Catalogs - Exportations`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier
* `pageNumber` - _required_ - The page number you want to get
* `pageSize` - _required_ - The entry count you want to get

### Get channel catalog product information list

*Tags:* `Channel Catalogs - Products`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier

### Get channel catalog products' counters

*Tags:* `Channel Catalogs - Products`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier

### Export channel catalog product information list

*Tags:* `Channel Catalogs - Products`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier
* `format` - _required_ - The file type of the exportation
    Possible values: xlsx, csv.

### Get channel catalog product information

*Tags:* `Channel Catalogs - Products`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier
* `productId` - _required_ - The product identifier

### Disable channel catalog product

> By default a all your catalog products are exposed to the channel.<br/>
> You can disable a product by using this operation.<br/>
> /!\ In case of massive optimisation we recommand you to use the analytics api

*Tags:* `Channel Catalogs - Products Optimisation`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier
* `productId` - _required_ - The product identifier

### Override channel catalog product values

*Tags:* `Channel Catalogs - Products Overrides`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier
* `productId` - _required_ - The product identifier

### Get channel catalog product value override compatibilities status

*Tags:* `Channel Catalogs - Products Overrides`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier
* `productId` - _required_ - The product identifier

### Copy channel catalog product value override

*Tags:* `Channel Catalogs - Products Overrides`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier
* `productId` - _required_ - The product identifier

### Delete a specific channel catalog product value override

*Tags:* `Channel Catalogs - Products Overrides`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier
* `productId` - _required_ - The product identifier
* `channelColumnId` - _required_ - The channel column identifier

### Reenable channel catalog product

> By default a all your catalog products are exposed to the channel.<br/>
> You can reenable a product by using this operation.<br/>
> /!\ In case of massive optimisation we recommand you to use the analytics api

*Tags:* `Channel Catalogs - Products Optimisation`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier
* `productId` - _required_ - The product identifier

### Configure channel catalog cost settings

*Tags:* `Channel Catalogs - Settings`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier

### Configure channel catalog general settings

*Tags:* `Channel Catalogs - Settings`

#### Input Parameters
* `channelCatalogId` - _required_ - The channel catalog identifier

### List all available channel for this store

*Tags:* `Channels - Channels Global`

#### Input Parameters
* `storeId` - _required_ - The store identifier

### Get channel information

*Tags:* `Channels - Channels Global`

#### Input Parameters
* `channelId` - _required_ - The channel identifier

### Get channel categories

*Tags:* `Channels - Channels Global`

#### Input Parameters
* `channelId` - _required_ - The channel identifier
* `Accept-Encoding` - _required_ - Indicates that the client accepts that the response will be compressed to reduce traffic size.

### Get channel columns

*Tags:* `Channels - Channels Global`

#### Input Parameters
* `channelId` - _required_ - The channel identifier
* `Accept-Encoding` - _required_ - Indicates that the client accepts that the response will be compressed to reduce traffic size.

### The index of all operations and LOV

*Tags:* `Customer - Global`

#### Input Parameters
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Get user account information

*Tags:* `Customer - Account`

#### Input Parameters
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Activate the user account

*Tags:* `Customer - Account`

### Change user password

*Tags:* `Customer - Account`

### Change company information

*Tags:* `Customer - Account`

### Get credit card information

*Tags:* `Customer - Account`

#### Input Parameters
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Save user credit card info

*Tags:* `Customer - Account`

### Save user personal information

*Tags:* `Customer - Account`

### Get profile picture information

*Tags:* `Customer - Account`

#### Input Parameters
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Change user picture information

*Tags:* `Customer - Account`

### Resend email activation

*Tags:* `Customer - Account`

### Get billing periods conditions

*Tags:* `Customer - Contracts`

#### Input Parameters
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Get contract list

*Tags:* `Customer - Contracts`

#### Input Parameters
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Create a new contract

> Now you are ready to create your contract. Before that, please ensure that you check the offer with the same request parameterts. /offers

*Tags:* `Customer - Contracts`

### Schedule termination of your current contract at the end of the commitment.

> By default your contract are automatically renew. By calling this operation you can disable the auto renewal.

*Tags:* `Customer - Contracts`

### Reactivate your terminated contract.

> By calling this operation you can re-enable the auto renewal.

*Tags:* `Customer - Contracts`

### Delete your next contract

*Tags:* `Customer - Contracts`

### Get friend information

*Tags:* `Customer - Friends`

#### Input Parameters
* `userId` - _required_ - Your friend user id
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Get all your invoices

*Tags:* `Customer - Invoices`

#### Input Parameters
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Get all standard offers

*Tags:* `Customer - Contracts`

#### Input Parameters
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Get offer pricing

> Get the offer pricing then you can create your contract with the same request parameters. /v2/user/customer/contracts

*Tags:* `Customer - Contracts`

### Log out the current user from go2

*Tags:* `Customer - Security`

### Get store list

*Tags:* `Customer - Stores`

#### Input Parameters
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Create a new store

*Tags:* `Customer - Stores`

### Delete a store

*Tags:* `Customer - Stores`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Get store's information

*Tags:* `Customer - Stores`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Update some store's information.

> Update some store's information. FYI, you cannot change the country.

*Tags:* `Customer - Stores`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Get store's alerts

*Tags:* `Customer - Alerts`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Save store alerts

> You just have to send the alert you want to update, does not need all alerts. (PARTIAL UPDATE ACCEPTED)

*Tags:* `Customer - Alerts`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Get store's rights

*Tags:* `Customer - Rights`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Get shares related to this store

*Tags:* `Customer - Shares`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Share a store to another user

*Tags:* `Customer - Shares`

#### Input Parameters
* `storeId` - _required_ - Your store identifier

### Delete a share of a store to another user

*Tags:* `Customer - Shares`

#### Input Parameters
* `storeId` - _required_ - Your store identifier
* `userId` - _required_ - The friend user id

### Get all list names

*Tags:* `User - List of Values - LOV`

### Get the list of values related to this list name

*Tags:* `User - List of Values - LOV`

#### Input Parameters
* `listName` - _required_ - The list of value name your want to get
* `Accept-Language` - _optional_ - Indicates that the client accepts the following languages.
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Get your marketplace channel catalog list

*Tags:* `Marketplaces - Channel catalogs - Global`

#### Input Parameters
* `storeId` - _optional_ - The StoreId to filter by

### Fetch the publication history for an account, sorted by descending start date

*Tags:* `Marketplaces - Channel catalogs - Publications`

#### Input Parameters
* `marketplaceTechnicalCode` - _required_ - Marketplace Technical Code to query (required)
* `accountId` - _required_ - Account Id to query (required)
* `channelCatalogId` - _optional_ - Channel Catalog Id by which to filter (optional)
* `count` - _optional_ - Amount of entries to fetch (optional, default set to 10)
* `publicationTypes` - _optional_ - Publication types by which to filter (optional)

### Get the marketplace properties for a channel catalog

*Tags:* `Marketplaces - Channel catalogs - Settings`

#### Input Parameters
* `channelCatalogId` - _required_
* `redirectionPageUrl` - _required_
* `Accept-Language` - _optional_ - Indicates that the client accepts the following languages.

### Get the marketplace settings for a channel catalog

*Tags:* `Marketplaces - Channel catalogs - Settings`

#### Input Parameters
* `channelCatalogId` - _required_ - Channel Catalog Id to query (required)

### Save new marketplace settings for a channel catalog

> Allow you to configure your marketplace settings.<br/>
> Partial update accepted.

*Tags:* `Marketplaces - Channel catalogs - Settings`

#### Input Parameters
* `channelCatalogId` - _required_ - Channel Catalog Id to query

### Get all actions you can do on the order API

*Tags:* `Marketplaces - Orders - Global`

#### Input Parameters
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Get list of configured automatic Order status transitions

*Tags:* `Marketplaces - Orders - AutoTransitions`

#### Input Parameters
* `storeId` - _optional_ - The StoreId to filter by
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Configure new or existing automatic Order status transition

*Tags:* `Marketplaces - Orders - AutoTransitions`

### Send a batch of operations to change your marketplace Order information (accept, ship, etc.)

> The purpose of this operation is to reduce the amount of request to the API.

*Tags:* `Marketplaces - Orders - Batches`

#### Input Parameters
* `changeOrderType` - _required_ - The Order change type
* `userName` - _required_ - Sometimes the user in the e-commerce application is not the same as user associated with the current subscription key. We recommend providing your application's user login.
* `testMode` - _optional_ - If true, the operation will be not be sent to marketplace. But the validation will be taken in account.

### Send a batch of operations to clear an Order's merchant information (max 100 items per call)

> The purpose of this operation is to reduce the amount of request to the API.

*Tags:* `Marketplaces - Orders - Batches`

### Send a batch of operations to set an Order's merchant information  (max 100 items per call)

> The purpose of this operation is to reduce the amount of request to the API.

*Tags:* `Marketplaces - Orders - Batches`

### Get a paginated list of Order report exportations

*Tags:* `Marketplaces - Orders - Exports`

#### Input Parameters
* `pageNumber` - _required_ - The page number you want to get
* `pageSize` - _required_ - The entry count you want to get
* `storeId` - _required_ - The store identifier to regroup the order exportations
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Request a new Order report exportation to be generated

> A new file will be generated containing a summary of all the Orders matching the requested filter settings.

*Tags:* `Marketplaces - Orders - Exports`

### Send harvest request to all your marketplaces

*Tags:* `Marketplaces - Orders - Global`

#### Input Parameters
* `storeId` - _optional_ - The StoreId to filter by

### Get a paginated list of all Orders with all Order and Order Item(s) properties

> The purpose of this operation is to reduce the amount of request to the API.\<br/>
> \<br/>
> Previous implmentation of this feature only returned a partial (light) version of the Orders. The purpose of this API is to reduce the number of incoming requests by returning the complete (full) Order and Order Item(s) properties.

*Tags:* `Marketplaces - Orders - List`

#### Input Parameters
* `Accept-Encoding` - _required_ - Allows the client to indicate wether it accepts a compressed encoding to reduce traffic size

### Get a paginated list of all Orders without details

*Tags:* `Marketplaces - Orders - List`

### Get current synchronization status between your marketplaces and BeezUP accounts

*Tags:* `Marketplaces - Orders - Global`

#### Input Parameters
* `storeId` - _optional_ - The StoreId to filter by
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Get full Order and Order Item(s) properties

*Tags:* `Marketplaces - Orders - Order`

#### Input Parameters
* `marketplaceTechnicalCode` - _required_ - The marketplace technical code
* `accountId` - _required_ - The account identifier
* `beezUPOrderId` - _required_ - The BeezUP Order identifier
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Get the meta information about the order (ETag, Last-Modified)

> The purpose of this operation is to reduce the bandwith usage by getting just the meta information about the order (ETag, Last-Modified) with the body.<br/>
> This could be useful

*Tags:* `Marketplaces - Orders - Order`

#### Input Parameters
* `marketplaceTechnicalCode` - _required_ - The marketplace technical code
* `accountId` - _required_ - The account identifier
* `beezUPOrderId` - _required_ - The BeezUP Order identifier
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Clear an Order's merchant information

*Tags:* `Marketplaces - Orders - Order`

#### Input Parameters
* `marketplaceTechnicalCode` - _required_ - The marketplace technical code
* `accountId` - _required_ - The account identifier
* `beezUPOrderId` - _required_ - The BeezUP Order identifier

### Send harvest request for a single Order

*Tags:* `Marketplaces - Orders - Order`

#### Input Parameters
* `marketplaceTechnicalCode` - _required_ - The marketplace technical code
* `accountId` - _required_ - The account identifier
* `beezUPOrderId` - _required_ - The BeezUP Order identifier

### Get an Order's harvest and change history

*Tags:* `Marketplaces - Orders - Order`

#### Input Parameters
* `marketplaceTechnicalCode` - _required_ - The marketplace technical code
* `accountId` - _required_ - The account identifier
* `beezUPOrderId` - _required_ - The BeezUP Order identifier
* `If-None-Match` - _optional_ - ETag value to identify the last known version of requested resource.\
To avoid useless exchange, we recommend you to indicate the ETag you previously got from this operation.\
If the ETag value does not match the response will be 200 to give you a new content, otherwise the response will be: 304 Not Modified, without any content.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


### Set an Order's merchant information

*Tags:* `Marketplaces - Orders - Order`

#### Input Parameters
* `marketplaceTechnicalCode` - _required_ - The marketplace technical code
* `accountId` - _required_ - The account identifier
* `beezUPOrderId` - _required_ - The BeezUP Order identifier

### Change your marketplace Order Information (accept, ship, etc.)

*Tags:* `Marketplaces - Orders - Order`

#### Input Parameters
* `marketplaceTechnicalCode` - _required_ - The marketplace technical code
* `accountId` - _required_ - The account identifier
* `beezUPOrderId` - _required_ - The BeezUP Order identifier
* `changeOrderType` - _required_ - The Order change type
* `userName` - _required_ - Sometimes the user in the e-commerce application is not the same as user associated with the current subscription key. We recommend providing your application's user login.
* `testMode` - _optional_ - If true, the operation will be not be sent to marketplace. But the validation will be taken in account.
* `If-Match` - _required_ - ETag value to identify the last known version of requested resource.\
To ensure that you are making a change on the lastest version of the resource.\
For more details go to this link: http://tools.ietf.org/html/rfc7232#section-2.3


## License

**flow**ground :- Telekom iPaaS / beezup-com-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
