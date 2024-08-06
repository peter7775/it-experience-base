`find . -type d -perm 777 -exec chmod 755 {} \;` 
(for changing the directory permission)

`find . -type f -perm 777 -exec chmod 644 {} \;` 
(for changing the file permission)



shell:

```
#!/usr/bin/bash
find . -type d -exec chmod 777 {} \;
find . -type f -exec chmod 644 {} \;
```