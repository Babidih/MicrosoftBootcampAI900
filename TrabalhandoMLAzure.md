# Trablhando Machine Learning na Prática no Azure ML
Aqui está o meu repertório GitHub para a entrega e futura avaliação de potenciais avaliadores do trabalho que realizei para a aprovação da 
atividade do bootcamp DIO da Microsoft: **_Microsoft Azure AI Fundamentals_**. Aqui tenho prints e explicações destes prints do passo a passo
realizado das ações realizadas para cumprir o desafio.

## Iniciando meu projeto
Para começar, realizei a criação e aprovação de minha conta Free Trial na Azure. Fiz as configurações necessárias e logo dei inicio a primeira atividade
do curso. Também realizei todo o curso no navegador **Chrome**. Isto é importante de destacar pois, por um motivo que desconheço até o dado momento de criação
desta documentação, tive problemas para realizar esta atividade atráves do meu navegador padrão, o **OperaGX**. Então, migrei para o Chrome e logo não tive mais 
problemas.

## Criando uma Ferramenta IA Para Prever Alugueis de Biciletas.
Vamos então ao passo a passo em si e suas respectivas explicações.

### Passo 1 - Selecionando a Ferramenta
Primeiro, devemos selecionar a ferramenta que queremos utilizar dentro do ambientge Azure para darmos início ao projeto. Então, você vai olhar para o menu 
que está localizado no canto esquerdo da página Azure, procurar a parte de **Criação** e selecionar a opção **ML automatizado**.

### Passo 2 
Tendo selecionado essa opção, devemos então inserir o nome do nosso BD, criar uma descrição para ele (não é necessário, porém ajuda a entender os dados em uma futura consulta
ou caso se tenha vários BDs) e selecionar a opção Tabular (caso já não esteja selecionado).

### Passo 3 
Feito isso, devemos selecionar a fonte de nossos dados. Selecione a opção "De Arquivos da Web", pois vamos inserir uma URL do BD.

### Passo 4
Seremos então direcionados para a etapa de inserção da URL e solicitar a validação daquele link e o BD nele contido. Aguarde alguns segundos.

### Passo 5
Feito essa validação, deveremos selecionar "Cabeçalhos de Coluna" e escolher a opção "Somente o primeiro arquivo tem cabeçalhos".

### Passo 6
Agora, estamos diante do Esquema. Confira se todas as opções estão marcadas, excluindo o "Path", e avançe. 

### Passo 7
Feito isso, eramos para a parte de Exame. Essa parte é dedicada para conferirmos as nossas configurações e as opções que inserimos. Feito essa verificação superficial, avançe para a 
próxima etapa. 

### Passo 8 
Feito tudo isso, devemos então selecionar a opção Regressão e selecionar o BD que importamos. 

### Passo 9
Devemos selecionar que nossa coluna de destino será o "rentals (integer)". Feito isso, devemos selecionar a engrenagem abaixo da opção que selecionamos "Exibir definição de configurações adicionais". Com isso, um menu lateral se abrirá. Devemos desmarcar todas as caixas que estejam marcadas. Para a opção **Metrica Primária** selecionamos a opção **Normalized root mean squared error**. Por fim, na opção **Modelos Permitidos** vamos selecionar duas opções: **RandomForest e LightGBM**. Até podemos selecionar mais, porém isso iria requerer mais tempo de compilação, então deixemos apenas estes dois mesmo.

### Passo 10
Por fim, vamos sair do menu lateral e expandir a aba **Limites**. Feito isso, iremos inserir os seguintes números, nas seguintes ordens: **3, 3, 3, 0.085, 15, 15**. Por fim, vamos habilitar a caixinha **Habilitar encerramento antecipado**

### Passo 11
Preenchidos todos esses números, vamos descer um pouco a página para a parte **Validar e Testar**. Vamos cilicar na primeira caixa e selecionar a opção **Divisão de validação de treinamento**. Deixe o número 10 mesmo. **Dados de teste** deverá ser **Nenhum**. 

### Passo 12
Vamos então para a parte de poder computacional. Deixe tudo padrão, porém se atente a parte **Tamanho da máquina virtual**. Olhe e veja se a opção selecionada é mesmo a **Standard_DS3_V2**. Tudo verificado, avançe.

### Passo 13 
Examine mais uma vez todas as configurações e opções selecionadas. Se tudo estiver certo, prossiga.

### Passo 14
O Azure vai dar início a criação da sua ferramenta de IA. Aguarde cerca de 8 a 12 minutos enquanto ele faz todos os preparativos. Atente-se ao **Status** dele, dentro de alguns segundos ele deverá mudar de **Não iniciado** para **Em execução**.

### Passo 15
Se tudo ocorreu bem, seu processo deverá estar concluido. Uma notificação aparecerá na sua caixa de notificações, avisando a conclusão da compilação, e o **Status** mudará para **Concluído** e ficará verde. Verifique a integridade de seus dados e se eles estão todos operando normalmente. Caso esteja tudo verificado e não houver nenhum problema, parabéns, sua ferramenta está criada.






























