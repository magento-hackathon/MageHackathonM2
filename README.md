# mage-hackathon.de on Magento 2
The idea is to port the current mage-hackathon.de in M2 and to make some usability improvements.

#### What it should be
Event is a normal product with attributes. Events have no pictures. 

The main menu is built of categories, one of which displays events, the rest contain CMS blocks.
The only filter on category page allows to show either passed or upcoming events. 

Nice idea would be to create an attribute with a custom renderer, which allowes to show maps (google or osm).

####Modules to develop:
 - GitHub authentication.
 - ideas (a guestbook by its structure)


####List of things to improve
* Empty homepage. It should display the events.
* Not sorted passed events: hard to find anything. Shoud be sorted by date.
* Unability to order discounted and normal tickets in one purchase
* The page with ideas has no pagination


#### Used themes and modules:
* [Mage Hackathon Theme](https://github.com/magento-hackathon/mage-hackathon-de-m2-theme)
* [mageplaza/magento-2-social-login](https://github.com/mageplaza/Magento-2-Social-Login-Extension)
* [splendidinternet/mage2-locale-de-de](https://github.com/splendidinternet/Magento2_German_LocalePack_de_DE)