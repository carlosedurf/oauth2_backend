#API comm OAUTH 2.0 - Laravel Passport

[fonte da implementação](https://laravel.com/docs/8.x/passport)

Feito como forma de consulta para quando for implementar em outro projeto.
<hr>

###Para facilitar a autenticação adicionei laravel ui com --auth

#### Passos a seguir:
* composer require laravel/ui
* php artisan ui bootstrap --auth
* php artisan migrate

<hr>

###Arquivos utilizados
* <strong>/routes/api.php</strong> = para fazer teste de obter informações 
* <strong>/app/Http/Kernel.php</strong> = Adicionante Client em $routeMiddleware 
* <strong>/app/Providers/AppServiceProvider.php</strong> = Para fazer hash unico de secret token (caso for utilizar) 
* <strong>/app/Providers/AuthServiceProvider.php</strong>
    * Adiciona leitura de rotas automaticamente
    * Setagem de client model para Client
    * Mudança de expiração de tokens
* <strong>/database/migrations/2021_04_22_133337_create_addresses_table.php</strong> = Para testar com a rota criada, se somente usuario autenticado pode obter sua informações de usuário
* <strong>/app/Models/Address.php</strong> = Para testar com a rota criada, se somente usuario autenticado pode obter sua informações de usuário já com relacionamento com usuário
* <strong>/app/Models/Passport/Client.php</strong> = Modal principal do client, feito herdando do Client do Passport para evitar tela de confirmação polimorfando o método skipsAuthorization()

