
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
- **bin/n98-magerun admin:user:change-password "user"** - altera senha de um admin





## Arquivos

xsd 
- responsáveis de trazer definições  de cada xml utilizado no magento
- como se fosse uma documentação técnica
- trás algumas vantagens
- bin/magento dev:urn-catalog:generate .idea/misc.xml -> cria definição dos xsd, no final aponta onde o arquivo deve ser gerado


## Injeção de Dependencia 

- Na injeção de dependencia no arquivo di.xml no preference, é passado qual a classe(interface) e o type que é a classe que será devolvida 


## Plugins 

- São classes que modificam classes publicas do magento
- Intercepta chamadas de métodos antes, depois ou em volta do que o método é chamado 
- serve para: corrigir bugs em módulos de terceiros, modificar ou acrescentar parâmetros em entidades antes delas serem salvas, disparar observers em lugares que não há eventos registrados. 
- tipos - before(modifica antes da classe), after(modifica depois da classe), around(modifica todo o método)
- são definidos no di.xml
- plugins são classes que referenciam a outras classes 

### Before
- usado para modificar parametros que são passados para o método 
- recebe: $subject + os demais parâmetros passados no método original 
- retorna: array com os novos valores dos parametros a ser passado para o método 
- $subject é a classe original que é recebida como parametro no método 
- se o método modificado não recebe parametro dele não deve ter retorno
- se o método modificado receber parametro deve haver um array retornando os parametros recebidos após o $subject


### After
- usado para modificar a saída de um método 
- recebe: #subject + $result + os demais parâmetros passados no método original
- retorna: novo resultado do método 

### Around 
- usado para modificar o método todo
- recebe: $subject + $proceed + os demais parâmetros passados no método original 
- retorna: o novo resultado, devendo chamar o $proceed



