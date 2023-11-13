# DIO.ModelandoOficinaMecanica
Repositório para o desenvolvimento do Desafio do Módulo - Modelando Projeto Conceitual da Formação SQL DataBase Specialist

# # **Descrição do Desafio**

Agora você irá criar um esquema conceitual do zero. A partir da narrativa fornecida você será capaz de criar todas as entidades, relacionamentos e atributos. Caso encontre algo que não foi definido na narrativa, utilize a sua compreensão do contexto e deixe uma descrição no README do seu github. para verificação.



### **Objetivo:**

Cria o esquema conceitual para o contexto de oficina com base na narrativa fornecida

### **Narrativa:**

-   Sistema de controle e gerenciamento de execução de ordens de serviço em uma oficina mecânica
-   Clientes levam veículos à oficina mecânica para serem consertados ou para passarem por revisões periódicas
-   Cada veículo é designado a uma equipe de mecânicos que identifica os serviços a serem executados e preenche uma OS com data de entrega.
-   A partir da OS, calcula-se o valor de cada serviço, consultando-se uma tabela de referência de mão-de-obra
-   O valor de cada peça também irá compor a OSO cliente autoriza a execução dos serviços
-   A mesma equipe avalia e executa os serviços
-   Os mecânicos possuem código, nome, endereço e especialidade
-   Cada OS possui: n°, data de emissão, um valor, status e uma data para conclusão dos trabalhos.

# # **Resolução**

 - Um **Cliente** ele pode ter mais de um **Veiculo**, como o veiculo pode  pertencer a mais de um **Cliente**. Com isso realizamos um relacionamento  de ***n:m***.
 - A **Ordem de Serviço** ela possui apenas um **Cliente,** porém um **Cliente** pode abrir mais de uma **OS**. Logo o relacionamento é de ***1:N***.
 - A **OS** ela é composta por uma **Equipe de Mecânicos** que brevemente  avaliaram qual será o *Tipo do serviço* a ser realizado.
 - A **Equipe de Mecânico** possui 1 ou mais **Mecânicos** e o **Mecânico** poderá participar apenas de uma **Equipe**, logo temos um relacionamento ***1:n***.
 - Mediante ao *tipo de serviço* identificado na **OS**, será informado uma ou mais **Serviço** para a **OS**. E o **Serviço** poderá ser utilizado em mais de uma **OS**. Sendo assim temos um relacionamento de ***n:m***.
 - Como o *valor do Serviço* é mutável, foi incluso um atributado  *ValorServiço* no relacionamento entre **OS** e **Serviços** para que seja  possível via aplicação calcular o valor dos serviços utilizados na **OS**.
 - No relacionamento de **OS** com **Peças**, utilizamos ***n:m***. Não sendo obrigatório a utilização da Peça na OS. E uma peça poderá ser utilizadas em mais de uma **OS.**
 - Como o valor da Peça poderá ser mutável, foi adicionado um atributo *valorPeça* no relacionamento entre **OS** e **Peça** para que seja possível fazer o calculo via aplicação do valor das peças utilizadas na *OS*.
 - Ainda na **OS** foi incluso um atributo *Autorizado*, mediante resposta o *Status* da **OS** irá mudar via aplicação.
