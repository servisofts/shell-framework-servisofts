# SFS JSON

```bash
#!/bin/bash

#JSObject
JSON obj_p new
# JSON obj_p parse "{alfo:asdpaz,obj:{nombre:ricky,apellido:paz,data:{nombre:a,apellido:p},edad:19,data2:{nombre:a,apellido:p}},objssas:{nombre:a,apellido:p}}" #Create new json object from str
JSON obj_p put "key" "valor"
JSON obj_p put "key2" "valor2"
# JSON obj_p parse "{component:comp,usuario:{nombre:ricky,apellido:paz}}" #Create new json object from str

# JSON obj_p keys
# JSON obj_p values
echo $obj_p
JSON obj_p get "key"

# resp=$()
# for obj in $resp; do
#     echo "$obj  "
# done
```