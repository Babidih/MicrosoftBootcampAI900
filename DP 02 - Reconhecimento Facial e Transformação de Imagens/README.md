# Passo a Passo do Desafio 02 - Reconhecimento Facial e transformação de imagens em Dados no Azure ML

## Criando Resource Pakage
Antes de entrarmos em toda a loucura de inserir imagens para a IA analisar, devemos primeiro criar um pacote de recursos com as configurações para ai sim termos contato com a IA. Abaixo estão o passo a passo para a realização dessa etapa:
### Passo 1
Primeiramente, devemos certificar de que estamos logados na nossa conta Azure ao acessar o link: [Portal Azure](https://portal.azure.com/?azure-portal=true). Tendo acessado sua conta, faremos o processo de criação do nosso pacote de recursos, com o processo similar ao feito no DP01, porém vamos por um caminho diferente:
Selecione a opção _**Ia + Machine Learning**_ (Seta Azul) e depois selecione a opção **Criar** no serviço  _**Serviços Cognitivos**_ (Seta Verde).
![Print0](https://github.com/Babidih/MicrosoftBootcampAI900/blob/main/DP%2002%20-%20Reconhecimento%20Facial%20e%20Transforma%C3%A7%C3%A3o%20de%20Imagens/Prints/Captura%20de%20tela%202024-02-28%20202839.png)

### Passo 2
Vamos agora configurar nosso pacote de serviço. Nossa _**Assinatura**_ (Seta Azul) não vamos mudar, deixaremos a padrão mesmo. Nosso _**Grupo de recursos**_ (Seta Verde), selecione algum que você já tenha criado (caso não tenha criado, crie um), a _**Região**_ é preferivel deixar no servidor **US** mesmo, quanto ao _**Nome**_ do nosso pacote de recursos você pode dar o nome que quiser. Por fim, nosso _**Tipo de Preço**_ a gente vai selecionar a opção **Standerd S0** (Seta Branca) e devemos marcar _**Caixa de Seleção**_ (Seta Amarela) e por fim clicar no botão _**Examinar + Criar**_ (Seta Laranja).
![Print01](https://github.com/Babidih/MicrosoftBootcampAI900/blob/main/DP%2002%20-%20Reconhecimento%20Facial%20e%20Transforma%C3%A7%C3%A3o%20de%20Imagens/Prints/Captura%20de%20tela%202024-02-28%20202839.png)

### Passo 3
Agora, vamos conferir todas as informações. Caso esteja tudo conforme a imágem abaixo, selecione o botão _**Criar**_ (Seta Azul).
![Print02](https://github.com/Babidih/MicrosoftBootcampAI900/blob/main/DP%2002%20-%20Reconhecimento%20Facial%20e%20Transforma%C3%A7%C3%A3o%20de%20Imagens/Prints/Captura%20de%20tela%202024-02-28%20203012.png)

### Passo 4
Agora que você solicitou a criação do pacote de recursos, devemos aguardar o proecesso - algo que não leva mais do que 1 ou 2 minutos. Note como fica o processo enquanto ele está em andamento (Imagem 1) e quando concluído (Imagem 2):
![Print03](https://github.com/Babidih/MicrosoftBootcampAI900/blob/main/DP%2002%20-%20Reconhecimento%20Facial%20e%20Transforma%C3%A7%C3%A3o%20de%20Imagens/Prints/Captura%20de%20tela%202024-02-28%20203034.png)
![Print04](https://github.com/Babidih/MicrosoftBootcampAI900/blob/main/DP%2002%20-%20Reconhecimento%20Facial%20e%20Transforma%C3%A7%C3%A3o%20de%20Imagens/Prints/Captura%20de%20tela%202024-02-28%20203044.png)

## Conectando Seu Recurso Serviço Azure AI com o Vision Studio
### Passo 1 
Vamos agora abrir um novo navegador e acessar o [Vision Studio](https://portal.vision.cognitive.azure.com/gallery/featured). Verifique se sua conta Azure estiver logada (Seta Azul). Caso não esteja, realize o login. Realizado o login, vamos selecionar o texto em azul escrito _**View All Resources**_ (Seta Verde). 
![Print04](https://github.com/Babidih/MicrosoftBootcampAI900/blob/main/DP%2002%20-%20Reconhecimento%20Facial%20e%20Transforma%C3%A7%C3%A3o%20de%20Imagens/Prints/Captura%20de%20tela%202024-02-29%20175355.png)
### Passo 2
Agora que estamos diante da escolha de um pacote de recurso, repare que ele está vazio, não contém nada. Ou, no meu caso, aparece apenas uma opção, mas não a que criamos. Sendo assim, vamos nos **três pontinhos** (Seta Azul) e vamos selecionar a opção _**Refresh**_. Com isso, nosso pacote de recursos apareceu. Selecione ele e depois clique no botão _**Select as Default Resource**_(Seta Azul).
![Print06](https://github.com/Babidih/MicrosoftBootcampAI900/blob/main/DP%2002%20-%20Reconhecimento%20Facial%20e%20Transforma%C3%A7%C3%A3o%20de%20Imagens/Prints/Captura%20de%20tela%202024-02-29%20175417.png)
![Print07](https://github.com/Babidih/MicrosoftBootcampAI900/blob/main/DP%2002%20-%20Reconhecimento%20Facial%20e%20Transforma%C3%A7%C3%A3o%20de%20Imagens/Prints/Captura%20de%20tela%202024-02-29%20175436.png)
Repare que depois de clicarmos no botão aconteceu... Nada! E tá tudo bem, provavlemnte deu tudo certo mesmo 😄, vamos para a próxima etapa agora.

## Detectando Rostos com Azure Vision
### Passo 1
Agora que selecionamos nosso Recurso, vamos voltar para a página [Vision Studio](https://portal.vision.cognitive.azure.com/gallery/featured). Estando lá, vamos selecionar a opção _**Face**_.
![Print08](https://github.com/Babidih/MicrosoftBootcampAI900/blob/main/DP%2002%20-%20Reconhecimento%20Facial%20e%20Transforma%C3%A7%C3%A3o%20de%20Imagens/Prints/Captura%20de%20tela%202024-02-29%20181252.png)<br>

Feito isso, vamos selecionar a única opção que aparece: _**Detect Faces in an Image**_:<br>

![Print09](https://github.com/Babidih/MicrosoftBootcampAI900/blob/main/DP%2002%20-%20Reconhecimento%20Facial%20e%20Transforma%C3%A7%C3%A3o%20de%20Imagens/Prints/Captura%20de%20tela%202024-02-29%20181306.png)

### Passo 2
Tendo acesso a ferramenta IA, vamos marcar a **Caixinha de Confirmação** (Seta Azul). Feito isso, agora temos duas opções: ou selecionamos arquivos nossos para ele realizar o procedimento de decção de rostos (Seta Preta) ou podemos esolher dentre as imagens que ele já trás para nós (Setas Verdes), fica a seu critério o que fazer.
![Print10](https://github.com/Babidih/MicrosoftBootcampAI900/blob/main/DP%2002%20-%20Reconhecimento%20Facial%20e%20Transforma%C3%A7%C3%A3o%20de%20Imagens/Prints/Captura%20de%20tela%202024-02-29%20181528.png)

### Passo 3
Tendo escolhido a imagem, vamos descer um pouco a página e ver o resultado. Na secção _**Detected Atributes**_ ele vai identificar para nós, como default, se há um rosto na imagem e, se sim, quantos há e se ele/s está/ão coberto/s por uma máscara. 
![Print11](https://github.com/Babidih/MicrosoftBootcampAI900/blob/main/DP%2002%20-%20Reconhecimento%20Facial%20e%20Transforma%C3%A7%C3%A3o%20de%20Imagens/Prints/Captura%20de%20tela%202024-02-29%20181355.png)
Já na parte JSON a gente tem mais detalhes sobre as informações coletadas pela IA com base nos aspectos físicos do rosto:
![Print12](https://github.com/Babidih/MicrosoftBootcampAI900/blob/main/DP%2002%20-%20Reconhecimento%20Facial%20e%20Transforma%C3%A7%C3%A3o%20de%20Imagens/Prints/Captura%20de%20tela%202024-02-29%20181409.png)
