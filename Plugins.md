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
