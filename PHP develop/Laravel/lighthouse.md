
### compile the GraphQL schema and cache it

`php artisan lighthouse:cache`

### clear the GraphQL schema cache

`php artisan lighthouse:clear-cache`



### create a class for a custom schema directive

`php artisan lighthouse:directive`

Use the --type, --field and --argument options to define where your directive can be used.


### create IDE helper files to improve type checking and autocompletion

`php artisan lighthouse:ide-helper`

This will create the following files:

- schema-directives.graphql: Schema definitions for directives you can use in your schema
- programmatic-types.graphql: Schema definitions for programmatically registered types, if you have any
- lighthouse_ide_helper.php: Class definitions for some magical PHP, such as the TestResponse mixin
	
### create a class for a GraphQL interface type

`php artisan lighthouse:interface <name>`

### create a class for a single field on the root Mutation type

`php artisan lighthouse:mutation <name>`

Use the option --full to include the seldom needed resolver arguments $context and $resolveInfo.


### compile the GraphQL schema and print the result

`php artisan lighthouse:print-schema`


### create a class for a single field on the root Query type

`php artisan lighthouse:query <name>`

Use the option --full to include the seldom needed resolver arguments $context and $resolveInfo.


### create a class for a GraphQL scalar type

`php artisan lighthouse:scalar <name>`



### create a class for a single field on the root Subscription type

`php artisan lighthouse:subscription <name>`



### create a class for a GraphQL union type

`php artisan lighthouse:union <name>`



### validate the GraphQL schema definition

`php artisan lighthouse:validate-schema`

* * *
https://lighthouse-php.com/5/api-reference/commands.html#cache