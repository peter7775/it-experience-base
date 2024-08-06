
`php bin/console doctrine:mapping:import "App\Entity" annotation --path=src/Entity`

#### generates getter/setter methods for all Entities
 `php bin/console make:entity --regenerate App`

#### generates getter/setter methods for one specific Entity
 `php bin/console make:entity --regenerate App\\Entity\\Country`