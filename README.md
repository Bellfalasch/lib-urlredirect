# Url Redirect Library

This library contains a URL content type, with an icon, and a controller mapping for all contents of this type, the controller handles the redirect to a given URL.

## Compatibility

| Lib version        | XP version |
| ------------- | ------------- |
| 2.0.0 | 6.12.0 |
| 1.0.0 | 6.2.0 |

The compatibility matrix shows official (tested) version support.

## Upgrading from 1.x to 2.x

With 2.x of this library we improved the usability of the library, but this also meant we had to break something.

To upgrade, just make sure you delete any URL template in Content Studio you have set up for 1.x **first**. The page controller it used is removed from the library in 2.x and will break.

After this, you can add the new library to your `build.gradle` and build the app again.

To get rendering to work, see under "Configuration".

## Configuration

From 2.x, you must add the following `Controller Mapping` to your main app's `site.xml` file. See the XP documentation for additional information on [Controller Mappings](http://xp.readthedocs.io/en/6.12/developer/site/mappings/index.html).

Add this code after the closing of the `<config>`-node, but within a `<mappings>`-node (or inside an existing one):

```
<mapping controller="/lib/enonic/url-redirect/index.js">
  <match>type:'url'</match>
</mapping>
```

## How to use

Just start creating contents of the type "URL" and visit it to be redirected to the defined URL. From inside Content Studio, redirects are disabled, but they can be tested via a link that will be displayed.

### Gradle 3+

```
plugins {
    id 'com.enonic.lib:urlredirect' version '2.0.0'
}
```

### Gradle - old

```
dependencies {
    include "com.enonic.lib:urlredirect:2.0.0"
}

repositories {
    maven {
        url 'http://repo.enonic.com/public'
    }
}
```
