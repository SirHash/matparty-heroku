-----------------------------
#DEPLOY DO ADONIS NO HEROKU
=============================
https://medium.com/@mazinosukah/how-to-deploy-adonisjs-apps-to-heroku-66741e7cd26f

OBS FEITAS
-----------------------------
1.O heroku não permite arquivo .env dentro do container, apaga todos.
2.heroku run bash // comando para roda o shel do heroku
3.Em produção: console.log(process.env) // comando que mostra todas as variveis em processo
4.Em produção: node ace <comando> // no heroku o comando "adonis" é igual a "node ace"
5.Em produção: ENV_SILENT=true node ace seed  --force // é necessário o ENV_SILENT=true(heroku não tem .env) e --force(produção)

PROCFILE
-----------------------------
release: ENV_SILENT=true node ace migration:run --force 
// ENV_SILENT para Adonis ignorar .env, pois o heroku já usa o "variaveis virtual"
// --force para roda em produção
web: ENV_SILENT=true npm start 

CONFIGURAR NO HEROKU AS VARIAVEIS
-----------------------------
DATABASE_URL 
DB_CONNECTION 

ADD-ONS
-----------------------------
Heroku Postgres :: Database
/////////////////////////////
