# Menu API for the Corporate Website
To get the header and footer data from the CCS website, you can simply do a GET request to the following domain depending on which environment you are working on:

Environment | Domain
------------ | -------------
DEV | https://webdev-cms.crowncommercial.gov.uk
PRE-PROD/UAT | https://webuat-cms.crowncommercial.gov.uk
PROD | https://webprod-cms.crowncommercial.gov.uk

<br>

![Screenshot of the Corporate Website's header and footer](https://github.com/Crown-Commercial-Service/CCS-Frontend-Kit/blob/main/docs/header_and_footer.png?raw=true "Screenshot of the Corporate Website's header and footer")

There are an endpoint for each of the menu we want and they are:

Location on the Website| Endpoint
------------ | -------------
Primary navigation | /wp-json/wp-api-menus/v2/menus/21
Secondary navigation | /wp-json/wp-api-menus/v2/menus/22
Sitemap | /wp-json/wp-api-menus/v2/menus/23
Quick links | /wp-json/wp-api-menus/v2/menus/24
About and contact | /wp-json/wp-api-menus/v2/menus/25

<br>

For example, if I want to get the menu option for Quick links in DEV, it will be:
https://webdev-cms.crowncommercial.gov.uk/wp-json/wp-api-menus/v2/menus/24

<br>

# Response from API

The API will response in a JSON format. Inside the Json object that it's return, we only want the `items` array which contain a list of links for the menu and we are only interested in the title and the url, which correspond to the button text and hyperlink.
