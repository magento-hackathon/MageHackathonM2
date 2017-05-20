# mage-hackathon.de on Magento 2
The idea is to port the current mage-hackathon.de in M2 and to make some usability improvements.

#### What it should be
Event is a normal product with attributes. Events have no pictures. 

The main menu is built of categories, one of which displays events, the rest contain CMS blocks.
The only filter on category page allows to show either passed or upcoming events. 

Nice idea would be to create an attribute with a custom renderer, which allowes to show maps (google or osm).

#### Modules to develop:
* ideas (a guestbook by its structure)


#### List of things to improve
* Not sorted passed events: hard to find anything. Shoud be sorted by date.
* The page with ideas has no pagination

#### Cool ideas
* List of participants
* Backend: Statistic of attribut in Backend: for example t-shirt sizes


#### Used themes and modules:
* [Mage Hackathon Theme](https://github.com/magento-hackathon/mage-hackathon-de-m2-theme)
* [mageplaza/magento-2-social-login](https://github.com/mageplaza/Magento-2-Social-Login-Extension)
* [splendidinternet/mage2-locale-de-de](https://github.com/splendidinternet/Magento2_German_LocalePack_de_DE)
* [MageSetup2](https://github.com/firegento/firegento-magesetup2)
* [Payone](https://github.com/PAYONE-GmbH/magento-2)

### Installation

'composer install'

#### Data Migration:
Install magento data migration tool

`composer require  magento/data-migration-tool:2.1.6` for magento2 2.1.6

Put `config.xml`and `map.xml` to `vendor/magento/data-migration-tool/etc/ce-to-ce/1.8.1.0` folder

Put `class-map.xml` , `map-eav.xml` and `eav-attribute-groups.xml` to `vendor/magento/data-migration-tool/etc/ce-to-ce` folder

**For local test**

Create your DB-Dump from your old shop.

Add following
```
INSERT INTO `eav_attribute` (`attribute_id`, `entity_type_id`, `attribute_code`, `attribute_model`, `backend_model`, `backend_type`, `backend_table`, `frontend_model`, `frontend_input`, `frontend_label`, `frontend_class`, `source_model`, `is_required`, `is_user_defined`, `default_value`, `is_unique`, `note`)
VALUES
    (121, 4, ‘enable_googlecheckout’, NULL, NULL, ‘int’, NULL, NULL, ‘select’, ‘Is Product Available for Purchase with Google Checkout’, NULL, ‘eav/entity_attribute_source_boolean’, 0, 0, ‘1’, 0, NULL);
````
Import DB

**Now the migration**

Change `<source>` and `<destination> in your config.xml

On console:
```
php bin/magento migrate:data vendor/magento/data-migration-tool/etc/ce-to-ce/1.8.1.0/config.xml
```

```
php bin/magento migrate:settings vendor/magento/data-migration-tool/etc/ce-to-ce/1.8.1.0/config.xml
```

Maybe you have to remove some eav_attribute.attribute_id entries