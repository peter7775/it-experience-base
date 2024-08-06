### generate controller

`php bin/console make:controller BrandNewController`

### generate an entire CRUD from a Doctrine entity, use:

`php bin/console make:crud Product`



### other possibility of make command

```
php bin/console list make

 make:command            Creates a new console command class
 make:controller         Creates a new controller class
 make:entity             Creates a new Doctrine entity class

 [...]

 make:validator          Creates a new validator and constraint class
 make:voter              Creates a new security voter class
```


### Creating your Own Makers

In case your applications need to generate custom boilerplate code, you can create your own make:... command reusing the tools provided by this bundle. To do that, you should create a class that extends AbstractMaker in your src/Maker/ directory. And this is really it!

For examples of how to complete your new maker command, see the core maker commands. Make sure your class is registered as a service and tagged with maker.command. If you’re using the standard Symfony services.yaml configuration, this will be done automatically.
