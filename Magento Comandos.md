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
