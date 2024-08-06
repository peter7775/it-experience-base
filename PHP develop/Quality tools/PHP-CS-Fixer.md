

# installation
with redirect vendor tools to special directory:
```
mkdir -p tools/php-cs-fixer
composer require --working-dir=tools/php-cs-fixer friendsofphp/php-cs-fixer
```

# fix all files
`{path}/php-cs-fixer fix src`

path - usuallly `php-cs-fixer fix src`

# repository + doc
https://github.com/PHP-CS-Fixer/PHP-CS-Fixer