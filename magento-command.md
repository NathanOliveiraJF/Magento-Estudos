
![[Pasted image 20230515215950.png]]

---

## Comandos Container

**bin/start** - inicia os containers
**bin/bash** - entra no container 
**bin/setup curso-m2.test**  - instala o magento bin/setup, curso-m2.test - nome da url da loja
**bin/cli php -i | grep xdebug** - configurações xdebug 
**bin/xdebug enable** - habilita 
**bin/xdebug disable** - disabilita
**bin/restart** - reinicia os containers

## Deploys

- default 
	- exceptions não são exibidas para o user final, mas são logadas em var/log
- developer
	- arquivos são gerados sobe demanda a cada request
	- exceptions são exibidos para o usuário e os logs são mais detalhados
	- baixa performance
	- não deve ser usado em produção, risco de segurança
- produção
	- não exibe erros no frontend, exceptions são gravas em logs
	- muito mais rapido
	- arquivos estaticos somente que estão em cache são exibidos

**altera o modo**

bin/magento deploy:mode:set developer -> altera para modo desenvolvedor
bin/magento deploy:mode:show -> mostra o modo atual


## bin/magento - Principais comandos 
- **bin/magento cache:clean** "cache"
- **bin/magento cache:flush**  "cache"
- **bin/magento cache:status** - exibe os "caches" habilitados
- **bin/magento cron:install** - instala as tarefas de cron
- **bin/magento deploy:mode:show** - mostra o modo de deploy 
- **bin/magento deploy:mode:set** - seta o modo de deploy
- **bin/magento indexer:info** - ver  o status da reindex de produtos
- **bin/magento indexer:reindexer** - reindex de todos os itens, atualiza itens
-  **bin/magento setup:upgrade** - usado quando é instalado um novo módulo em nossa loja, executa todos os scritps de setup dos módulos ou módulo que acabamos de instalar. Habilita um módulo novo.

## Ferramentas

**n98-magerun** - conjunto de comandos para trabalhar com magento
- **bin/n98-magerun admin:user:list** - lista os admins
- **bin/n98-magerun admin:user:change-password "user" - altera senha de um admin





## Arquivos

xsd 
- responsáveis de trazer definições  de cada xml utilizado no magento
- como se fosse uma documentação técnica
- trás algumas vantagens
- bin/magento dev:urn-catalog:generate .idea/misc.xml -> cria definição dos xsd, no final aponta onde o arquivo deve ser gerado
