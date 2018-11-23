# Sammlung von Tools und Infos

## Overpass - API

https://overpass-turbo.eu/

```
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
