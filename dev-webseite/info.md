# Sammlung von Tools und Infos

## Overpass - API

https://overpass-turbo.eu/

```xml
 <osm-script output="xml">
   
   
   <query type="relation">
      <has-kv k="admin_level" regv="9"/>
      <has-kv k="name" regv="Bonn"/>
      <bbox-query {{bbox}}/>
    </query>   
    
  
  <union>
    <item/>
    <recurse type="down"/>
  </union>

   <print mode="meta"/>

</osm-script>
```

## Beispiel für das THW

```js
(
  way["operator"="Bundesanstalt Technisches Hilfswerk (THW)"];
  >;
  node["operator"="Bundesanstalt Technisches Hilfswerk (THW)"];
);
out skel;
```

## PLZ Suche

```js
/* Zeige alle Elemente innerhalb einer Grenzrelation mit postal_code=x,
   welche ein Merkmal addr:postcode <> x haben */

{{plz=53343}} 
/* die PLZ hier beliebig ändern ... es muss allerdings die gültige PLZ
   einer vorhandenen Grenzrelation sein */

rel[postal_code="{{plz}}"];(._;>;);out;
/* diese Zeile dient nur zur Visualisierung der hoffentlich vorhandenen
   Grenzrelation ... ggf. auskommentieren oder löschen! */

area[postal_code="{{plz}}"]->.a;
(node(area.a)["addr:postcode"]["addr:postcode"!="{{plz}}"];
 way(area.a)["addr:postcode"]["addr:postcode"!="{{plz}}"];)
;(._;>;);out;
/* ... oben auf Ausführen klicken (oder Strg-Enter), und ggf. in der
   Karte mit Klick auf das Lupensymbol auf die hoffentlich erscheinenden
   Daten zoomen lassen */
   ```
