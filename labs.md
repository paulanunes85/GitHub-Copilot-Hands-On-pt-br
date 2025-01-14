<h1 align="center"> GitHub Copilot - A Ferramenta de Desenvolvimento de IA Mais Amplamente Adotada do Mundo</h1>
<h5 align="center">Revisão para Português Brasil @paulanunes85 - 2025</h5>

## Workshop Prático

Revisão 1.2 - 12/08/24

**As versões de diálogos, botões, etc. mostradas nas capturas de tela podem diferir da versão atual do Copilot**

**NOTA: Para copiar e colar no codespace, você pode precisar usar comandos de teclado - `CTRL-C` e `CTRL-V` (ou os comandos de teclado apropriados para seu sistema operacional).**

## Introdução
Bem-vindo ao Workshop Prático do GitHub Copilot! Neste workshop, você aprenderá a usar o GitHub Copilot, a ferramenta de desenvolvimento de IA mais amplamente adotada do mundo. O GitHub Copilot é um programador parceiro de IA que ajuda você a escrever código mais rápido e com menos erros. Ele é alimentado pelo Modelo de Linguagem Grande (LLM) da OpenAI, que é um modelo de linguagem de última geração treinado em uma ampla gama de fontes de dados, incluindo código disponível publicamente no GitHub. O GitHub Copilot está disponível como uma extensão para o Visual Studio Code e pode ser usado em qualquer linguagem, incluindo Python, JavaScript, TypeScript, Go, Ruby, Java, C++, e muitas outras.

## Antes de começar

### 1. Siga as instruções de inicialização no [arquivo README.md](README.md) SE AINDA NÃO FEZ ISSO!

### 2. Revise a instalação da Extensão do GitHub Copilot

Uma das vantagens de usar **GitHub Codespaces** para este workshop é que **GitHub Copilot** está pré-configurado para você.
1. Abra `.devcontainer/devcontainer.json`.

2. Se não estiver visível, role para baixo até ver a seção `"extensions"`.

3. Observe como as extensões `GitHub.copilot` e `GitHub.copilot-chat` já estão instaladas.

![Extensões do GitHub Copilot já estão instaladas](./images/pic005.png?raw=true "Extensões do GitHub Copilot já estão instaladas")

Se você estivesse usando o aplicativo **Visual Studio Code**, teria que instalar manualmente as extensões **GitHub Copilot**. Consulte [Configurar o GitHub Copilot no VS Code](https://code.visualstudio.com/docs/copilot/setup) para instruções passo a passo.

**NOTA:** Você também pode usar o **GitHub Copilot** no [Visual Studio](https://docs.github.com/en/copilot/quickstart?tool=visualstudio) e em [IDEs compatíveis com JetBrains](https://docs.github.com/en/copilot/quickstart?tool=jetbrains).

Agora você pode fechar `.devcontainer/devcontainer.json`, pois não precisaremos dele para mais nada neste laboratório.

### 3. Configure sua área de trabalho para manter o LABS.MD sempre visível

Antes de começarmos, configuraremos as janelas do navegador para manter o arquivo labs.md sempre visível. Isso permitirá que você alterne facilmente entre as instruções do laboratório e qualquer janela do editor que você tenha aberto.
1. Selecione a aba labs.md e arraste-a para baixo para que ela se mova para uma janela separada.

2. Se você estiver no Windows, pode "encaixar" a aba labs.md em um lado ou outro e selecionar a aba Codespace como a janela adjacente.

3. Mova o controle deslizante vertical até que você possa ver confortavelmente as instruções em labs.md e o Codespace lado a lado.

Agora podemos ver o arquivo labs.md de um lado da tela enquanto executamos as ações no Codespace do outro lado da tela. Se necessário, ajuste o nível de zoom em uma ou ambas as janelas conforme desejado.

![Visualização Dividida](./images/pic001.png?raw=true "Visualização Dividida")

### 4. Mude para a versão Insiders do Visual Studio Code no navegador

Se você estiver usando o cliente web do VS Code, pode mudar para a versão Insiders do aplicativo para garantir que está trabalhando com a versão mais recente. Para mais informações sobre esta versão do VS Code, veja [Introducing the Insiders Build](https://code.visualstudio.com/blogs/2016/02/01/introducing_insiders_build) no blog do VS Code.

Depois de mudar de versão em um codespace, o cliente web continuará a usar a versão Insiders se você parar e reiniciar o codespace. Novos codespaces que você criar e abrir no cliente web do VS Code também usarão a versão Insiders.

1. No canto inferior esquerdo da janela do navegador que está exibindo um codespace, clique.

2. No menu, selecione `Switch to Insiders Version`.

![Mudar para a Versão Insiders](./images/pic014.png?raw=true "Mudar para a Versão Insiders")

3. Clique em **Reload**.

Para voltar à versão Stable do VS Code, repita o processo, mas escolha `Switch to Stable Version`. Depois de mudar de volta, o codespace continuará a usar a versão Stable se você parar e reiniciar o codespace. Novos codespaces que você criar e abrir no cliente web do VS Code também usarão a versão Stable.

### 5. Deixe-nos saber como estamos indo
<!-- Instruir os participantes do laboratório a utilizarem as discussões do GitHub encontradas aqui: https://github.com/DaveOps30/copilot-hands-on/discussions -->
<!-- Referenciar especificamente as categorias "Workshop Feedback & Suggestions" e "Workshop Issues" -->
Estamos utilizando [**Discussões do GitHub**](https://github.com/DaveOps30/copilot-hands-on/discussions) localizadas neste repositório para relatórios de problemas em tempo real, feedback e sugestões.
- Se você encontrar algum problema ou precisar de ajuda, por favor, poste na categoria de discussão [`Workshop Issues`](https://github.com/DaveOps30/copilot-hands-on/discussions/categories/workshop-issues). Certifique-se de verificar as discussões existentes para ver se sua pergunta já foi respondida. Também temos vários monitores na sala para ajudar a responder suas perguntas e resolver problemas. Por favor, levante a mão e nós o ajudaremos.
- Se você tiver algum feedback ou sugestões de melhoria, por favor, nos avise na categoria de discussão [`Workshop Feedback & Suggestions`](https://github.com/DaveOps30/copilot-hands-on/discussions/categories/workshop-feedback-suggestions).
- Quando você encontrar algo que queira compartilhar, por favor, poste na categoria de discussão [`Show and Tell`](https://github.com/DaveOps30/copilot-hands-on/discussions/categories/show-and-tell).

## Lab 1 - Usando o GitHub Copilot para aprender sobre o GitHub Copilot

**Objetivo: Neste laboratório, começaremos a aprender sobre o GitHub Copilot fazendo perguntas ao GitHub Copilot sobre o GitHub Copilot.**

Uma maneira de interagir com o GitHub Copilot é usar a interface de chat. Esta é uma ótima maneira de fazer perguntas sobre o GitHub Copilot, pois é uma interface de linguagem natural e foi treinada em uma ampla variedade de recursos.

1. Selecione o ícone da extensão Chat para abrir a janela de chat. Vamos começar com uma solicitação básica sobre o GitHub Copilot. Digite o texto a seguir na caixa de prompt.

```
Dê-me algumas sugestões de maneiras eficazes de usar o GitHub Copilot.
```
![Sugestões do Copilot](./images/pic015.png?raw=true "Sugestões do Copilot")

Observe como o GitHub Copilot Chat fornece uma sugestão para sua próxima pergunta. Esta é uma ótima maneira de manter a conversa fluindo. Se você gostar da sugestão, basta clicar no link para usá-la. Se não gostar da sugestão, basta ignorá-la e digitar sua própria pergunta.

2. Agora que temos algumas sugestões, vamos pedir alguns **exemplos específicos** de comandos ou prompts que podem ser usados com o GitHub Copilot. Digite a seguinte pergunta na caixa de prompt.

```
Quais são alguns exemplos de comandos ou prompts específicos que podem ser usados para interagir com o GitHub Copilot?
```
![Exemplos do Copilot](./images/pic017.png?raw=true "Exemplos do Copilot")

3. Cobrimos alguns dos conceitos básicos, vamos perguntar sobre **como obter o máximo do GitHub Copilot**. Digite a seguinte pergunta na caixa de prompt.

```
Sou novo no GitHub Copilot. Como obter o máximo do GitHub Copilot?
```
![Obter o máximo do Copilot](./images/pic019.png?raw=true "Obter o máximo do Copilot")

4. Uma das chaves para obter o máximo dos modelos de IA é fornecer o **contexto** certo. Vamos perguntar sobre isso. Digite a seguinte pergunta na caixa de prompt.

```
O que o GitHub Copilot usa como contexto ao usar IA para gerar sugestões de código?
```
![Contexto para o Copilot](./images/pic021.png?raw=true "Contexto para o Copilot")

5. Falando em contexto, existem algumas **palavras-chave contextuais comuns** que podem ser usadas nos prompts do GitHub Copilot. Vamos perguntar sobre elas. Digite a seguinte pergunta na caixa de prompt.

```
Quais são algumas palavras-chave contextuais comuns que podem ser usadas nos prompts do GitHub Copilot?
```
![Palavras-chave contextuais](./images/pic022.png?raw=true "Palavras-chave contextuais")

6. O que mais podemos fazer no painel de chat?

Vamos ver se podemos usar o chat para aprender mais sobre as capacidades do Copilot. Digite o seguinte no painel de chat e pressione `Enter`.

```
/help
```
![Saída de /help](./images/pic012.png?raw=true "Saída de /help")

Como você pode ver na saída, há um número crescente de `Participantes` e `Variáveis` que você pode usar no **GitHub Copilot Chat**. Por exemplo, reveja a saída para responder a estas perguntas:
- Qual `Participante` você usaria para obter o significado das linhas selecionadas no terminal?
- Qual `Variável` você usaria para fornecer um arquivo específico ao **GitHub Copilot Chat** como contexto, mesmo que esse arquivo não esteja aberto no momento?

7. Outra chave para usar o GitHub Copilot de forma eficaz é entender os conceitos básicos de **engenharia de prompts**. Digite a seguinte pergunta na caixa de prompt.

```
Alguém mencionou "Engenharia de Prompts". Explique-me os conceitos básicos de engenharia de prompts.
```
![Engenharia de Prompts](./images/pic018.png?raw=true "Engenharia de Prompts")

8. O GitHub está sempre trabalhando para garantir que você possa obter o máximo do GitHub Copilot. Vamos perguntar sobre qual versão do Chat GPT está sendo usada.

```
Qual versão do Chat GPT você está usando?
```
![Versão do Chat GPT](./images/pic016.png?raw=true "Versão do Chat GPT")

9. O GitHub Copilot está sendo atualizado frequentemente. Vamos perguntar como podemos nos manter atualizados com os últimos recursos e anúncios.

```
Como posso me manter atualizado sobre novos recursos e anúncios do GitHub Copilot?
```
![Manter-se atualizado](./images/pic020.png?raw=true "Manter-se atualizado")

Agora que o GitHub Copilot explicou os conceitos básicos e algumas das chaves para usá-lo de forma eficaz, vamos tentar usá-lo para **gerar algum código**.

**=========== FIM DO LAB ===========**

## Lab 2 - Aprendendo a criar bons prompts para o Copilot

**Objetivo: Neste laboratório, começaremos a aprender sobre o Copilot e como ele gera código com base nos prompts que fornecemos**

1. Crie um novo arquivo. No terminal, digite

   ```
   code index.js
   ```

2. Depois disso, este arquivo deve estar aberto em uma aba no editor.

3. Vamos ver como o Copilot responde a uma solicitação genérica. Vá para essa aba e digite um comentário que diz

```
// função para analisar dados
```
4. Pressione Enter e observe o código que o Copilot sugeriu. Isso provavelmente é mais genérico do que queremos, mas pressione Tab para selecionar essa linha. (Observe que você deve dar um segundo para o Copilot fornecer sugestões de código antes de continuar para a próxima linha.)

5. Depois de pressionar Tab, o Copilot gerará outra parte da função. (Se não, você pode precisar pressionar Enter.) Pressione Tab para aceitá-la. Continue até obter uma função completa (ou o Copilot parar de gerar sugestões adicionais de código). Um exemplo de como o código pode parecer está abaixo.

![Função gerada pelo Copilot](./images/cpho5.png?raw=true "Função gerada pelo Copilot")

6. Este prompt não é específico o suficiente para o Copilot interpretar o que queremos fazer. Destaque o código e exclua-o, para que possamos tentar novamente.

7. Agora digite um comentário no topo que diz

```
// função para analisar URL
```
8. Pressione Enter e você provavelmente verá uma linha semelhante a

```
function parseURL(url) {
```

9. Basta pressionar Tab para aceitá-la e Enter novamente. Pause. Depois disso, o Copilot pode ou não oferecer uma sugestão. Se oferecer, ótimo - você pode simplesmente pressionar Tab e aceitá-la. Se não, pode ser necessário "cutucar" o Copilot fornecendo mais prompts. Somente se você não estiver recebendo respostas do Copilot, pressione Enter e digite o comentário abaixo para cutucar o Copilot.

```
// analisar URL
```
![comentário de cutucada](./images/cdd3.png?raw=true "comentário de cutucada")

10. Somente se necessário, pressione Enter e o Copilot deve começar a gerar sugestões novamente. Pause após cada Enter para dar ao Copilot uma chance de sugerir código. Então você pode simplesmente pressionar Tab para aceitar cada linha e depois Enter para obter a próxima parte do código até que a função esteja completa. Você pode obter algumas linhas em branco ao longo do caminho ou, para algumas linhas, pode precisar pressionar Tab duas vezes para aceitar o código se ele estiver mais indentado. Mas basta pressionar Enter até chegar ao final de uma função. (Você estará no final quando a indentação estiver concluída. Além disso, o Copilot pode começar a sugerir outra função em comentários como // teste...)

11. Suponha que você não esteja satisfeito com essa sugestão. O Copilot pode fornecer outras opções para o código. Para vê-las, certifique-se de estar no editor do arquivo, depois exclua todas as linhas, exceto a primeira linha da função **e** coloque o cursor no final da primeira linha.

![reset para escolhas alternativas](./images/cdd105.png?raw=true "reset para escolhas alternativas")

12. Pressione **Ctrl + Enter**. Uma segunda janela será aberta com outras sugestões.
Seja paciente - leva um pouco de tempo para o Copilot gerar sugestões alternativas. Depois de um momento, você terá até 10 alternativas para escolher. Estas serão de qualidade e completude variadas. Você pode percorrê-las e escolher uma, se adequada, clicando no botão **Accept suggestion #** abaixo da sugestão alternativa. Observe que isso adicionará o código ao conjunto existente, então você pode precisar fazer algumas edições menores depois.

![sugestões alternativas](./images/cdd106.png?raw=true "sugestões alternativas")

13. Vamos fazer mais uma tentativa de obter um prompt específico para o Copilot. Exclua todo o código atualmente em index.js. Desta vez, não digitaremos um comentário, mas sim um nome de função específico.
Digite o seguinte no arquivo vazio. (Não há parênteses após o texto *splitURLandReturnComponents*.) Não pressione Tab ou Enter ainda.

```
function splitURLandReturnComponents
```

14. Com este nome de função, o Copilot deve sugerir uma definição de função completa - na verdade, pode sugerir várias. Para ver as opções, passe o mouse sobre a primeira linha e uma pequena janela aparecerá. Esta janela mostrará quantas opções existem (provavelmente 2 ou 3) e fornecerá links "<" e ">" para alternar entre elas. Clique nos botões "<" e ">" para ver as diferenças nas sugestões disponíveis.

![sugestões alternativas inline](./images/cdd5b.png?raw=true "sugestões alternativas inline")

15. Quando encontrar uma alternativa que goste, vá em frente e pressione Tab para selecioná-la.

**=========== FIM DO LAB ===========**

## Lab 3 - Usando o Copilot para simplificar e explicar código

1. Crie um novo arquivo chamado prime.py. Crie-o através do mesmo processo que usamos no Lab 2, digitando a linha abaixo no terminal.

```
code prime.py
```

2. Comece digitando uma definição de função como abaixo
```
def is_prime(n):
```
3. Deixe o cursor no final da linha.

![ponto de partida](./images/cdd104.png?raw=true "ponto de partida")

4. Pressione **Ctrl+Enter** para ver as opções

5. Escolha uma das opções que seja mais longa e/ou mais complexa (se houver) e **Accept suggestion #**. Se não houver uma que seja mais longa/complexa, basta escolher uma alternativa e **Accept suggestion #**.

![sugestões alternativas](./images/cdd34b.png?raw=true "sugestões alternativas")

6. Destaque o código e selecione o ícone da extensão Chat para abrir a janela de chat. Diga ao Copilot para simplificar o código digitando na janela de chat.
```
simplificar
```

![simplificando via caixa de chat](./images/cdd35.png?raw=true "simplificando via caixa de chat")

7. Passe o mouse sobre o texto simplificado e diga ao Copilot para inserir a sugestão no cursor para substituir o texto que está lá atualmente.

![substituir pela sugestão do chat](./images/cdd143.png?raw=true "substituir pela sugestão do chat")

8. Agora, vamos introduzir um erro no código para ver como o Copilot pode corrigi-lo. Escolha uma instância de um nome de variável e mude para um que não exista. Por exemplo, mude uma instância de "n" para "x".

![introduzir erro](./images/cdd37b.png?raw=true "introduzir erro")

9. Observe o ícone de lâmpada que apareceu. Clique nele, role para baixo (se necessário) e você terá opções adicionais para corrigir ou explicar com o Copilot.

![opções do Copilot inline](./images/cdd38b.png?raw=true "opções do Copilot inline")

10. Vá em frente e clique na opção "Fix using Copilot".

11. Depois de alguns momentos, ele deve propor uma correção que você pode simplesmente aceitar (via o botão Accept). Você também pode clicar no ícone *Show Changes* para ver antes/depois das alterações propostas. (Se ele não propor uma correção no diálogo, você pode pular para o passo 12 e usar o comando /fix no chat em vez disso.)

![Corrigindo com o Copilot](./images/cdd107a.png?raw=true "Corrigindo com o Copilot")

12. (Opcional) Se desejar, você pode voltar e fazer o erro novamente, destacar o código e depois usar o comando /fix na janela de chat para obter os mesmos resultados.

**=========== FIM DO LAB ===========**

## Lab 4 - Usando o Copilot após a codificação

**Objetivo: Neste laboratório, veremos algumas outras maneiras de aproveitar o Copilot após a codificação inicial estar concluída**

1. Agora que temos algum código para trabalhar, vamos ver o que mais o Copilot pode fazer por nós. Vamos pedir para ele explicar o código atual em nosso arquivo *prime.py*. Selecione o código. Em seguida, use as teclas **Cmd+I** para abrir o diálogo de chat interativo do Copilot.

![Dizendo interativamente ao Copilot para explicar o código](./images/cdd40b.png?raw=true "Dizendo interativamente ao Copilot para explicar o código")

2. Diga ao Copilot para explicar o código digitando o comando abaixo no diálogo. Pressione Enter. Em seguida, você deve ver a saída no diálogo. Clique no botão *View in Chat* para ver a saída na janela de chat separada.

```
/explain
```
![Saída de dizer interativamente ao Copilot para explicar o código no diálogo](./images/cdd144.png?raw=true "Saída de dizer interativamente ao Copilot para explicar o código no diálogo")
![Saída de dizer interativamente ao Copilot para explicar o código](./images/cdd41b.png?raw=true "Saída de dizer interativamente ao Copilot para explicar o código")

3. Agora, vamos fazer a mesma solicitação, mas através de um comentário. No arquivo *prime.py*, abaixo do código, digite o seguinte comentário e pressione Enter.
```
# explique o código acima linha por linha
```
4. Depois disso, o Copilot deve começar a mostrar a explicação em comentários. Basta pressionar Tab para aceitar cada linha e depois Enter para passar para a próxima.

![Saída de dizer ao Copilot para explicar o código via comentário](./images/cdd42b.png?raw=true "Saída de dizer ao Copilot para explicar o código via comentário")

5. Também podemos consultar o Copilot inline fazendo uma pergunta em um comentário. Exclua a explicação comentada e tente a pergunta abaixo. Para ser claro, você pode prefixá-la com :q, mas isso não é necessário com o recurso de chat instalado.

```
# q: o que a função acima faz?
```

![Solicitando o que o código faz com q:](./images/cdd43b.png?raw=true "Solicitando o que o código faz com q:")

6. Finalmente, vamos ver como usar o recurso doc para documentar automaticamente nosso código. Destaque o código real.

7. Agora, digite **Cmd+I** e digite o comando **/doc**. Depois de alguns momentos, o Copilot deve gerar alguma documentação para o código. Você pode ir em frente e *Accept* as alterações.

![Doc gerado para o código](./images/cdd44d.png?raw=true "Doc gerado para o código")

8. Embora isso seja uma documentação útil para o início da função, gostaríamos de ter comentários mais extensos no corpo da função. Então, vamos obter a ajuda do Copilot com isso. Abra o diálogo de chat novamente com **Cmd+I** e digite o texto "comente este código de forma verbosa". Depois que o Copilot concluir suas sugestões, se você estiver satisfeito com elas, pode simplesmente clicar em *Accept*.

![Regenerando doc](./images/cdd110.png?raw=true "Regenerando doc")

9. Quando encontrar um exemplo de doc que goste, vá em frente e clique em **Accept**.

**=========== FIM DO LAB ===========**

## Lab 5 - Usando o Copilot para gerar testes

**Objetivo: Neste laboratório, veremos alguns exemplos de como o Copilot pode gerar testes**

1. Comece no arquivo *prime.py* que estamos usando. Posicione o cursor abaixo do código.

2. Digite um comentário para criar testes unitários
```
# crie uma função para fazer 5 testes unitários do código acima
```

3. *Se você não receber uma sugestão*, digite o código abaixo para começar a cutucar. Caso contrário, você pode simplesmente aceitar a sugestão.

```
def test_is_prime():
```
![gerando testes via comentário](./images/cdd46a.png?raw=true "gerando testes via comentário")

4. E se não soubéssemos como testar o código? Vamos perguntar ao Copilot. Destaque a função *is_prime()*.

![selecionando código](./images/cdd111.png?raw=true "selecionando código")

5. Agora, mude para a interface de chat e pergunte ao Copilot usando o prompt a seguir:

```
#selection: Como eu testo este código?
```
![solicitando como testar](./images/cdd112.png?raw=true "solicitando como testar")

6. Depois de digitar isso, você deve ver uma explicação de como testar o código junto com o código de teste sugerido. Se você expandir a referência na saída do chat, poderá ver que ele usou apenas as linhas selecionadas.

![explicação de teste](./images/cdd113.png?raw=true "explicação de teste")

7. Vamos ver o que o comando de atalho faria. No diálogo de chat, digite "/tests" e depois Enter. O Copilot vai querer adicionar o agente *@workspace* ao comando. Basta remover o *@workspace* do início do comando. **Não pressione Enter ainda**.
```
/tests
```
8. Digite um sinal de hash/cerquilha após /tests. Neste ponto, o Copilot deve apresentar um diálogo de seleção. Escolha #file no menu.
```
/tests #
```

![comando de teste de atalho](./images/cdd140.png?raw=true "comando de teste de atalho")

9. Um diálogo aparecerá perto do topo do codespace com uma seleção de arquivos. Selecione o arquivo *prime.py* para completar o comando.

![diálogo de escolha de arquivo](./images/cdd141.png?raw=true "diálogo de escolha de arquivo")

10. Depois que o comando parecer */tests #file:prime.py*, vá em frente e pressione Enter para ver os resultados do teste sugeridos.

![diálogo de escolha de arquivo](./images/cdd142.png?raw=true "diálogo de escolha de arquivo")

11. Podemos colocar isso em um novo arquivo passando o mouse sobre a saída na janela de Chat, depois selecionando os "..." no menu pop-up e selecionando "Insert into new file". Vá em frente e selecione essa opção e então você terá um novo arquivo no seu editor com o código que você pode salvar conforme necessário.

![Inserir testes em um novo arquivo](./images/cdd115a.png?raw=true "Inserir testes em um novo arquivo")

**=========== FIM DO LAB ===========**

## Lab 6 - Usando o Copilot para ajudar com SQL

**Objetivo: Neste laboratório, veremos alguns exemplos de como o Copilot pode ajudar a escrever SQL**

1. Crie um novo arquivo chamado dev.sql. Você pode criá-lo digitando a linha abaixo no terminal.

```
code dev.sql
```

2. Depois disso, este arquivo deve estar aberto em uma aba no editor. Suponha que queremos trabalhar com um banco de dados ou definição de banco de dados que define um conjunto de dados para estudantes, funcionários, currículos, cursos, escolas de estudo, locais e registros para um sistema universitário. Vamos ver o que o Copilot geraria para uma consulta para obter todos os alunos em um curso - sem nenhum outro contexto.

Digite o seguinte comentário abaixo e pressione Tab para aceitar as sugestões. Lembre-se de que você pode precisar pressionar Enter várias vezes para que o Copilot faça o prompt. Ou, se você não receber uma sugestão ou apenas receber um comentário, tente "cutucar" o Copilot digitando "select".
```
-- defina uma instrução select para obter todos os alunos matriculados em um curso
```
3. Vá em frente e salve este arquivo como parte do projeto. Você pode fazer isso no menu de "3 linhas" em Arquivo->Salvar, ou simplesmente clicar no X ao lado do nome do arquivo na aba e selecionar Salvar.

![Salvar arquivo sql](./images/cdd96.png?raw=true "Salvar arquivo sql")

4. Se o arquivo não estiver mais aberto nas abas, você pode selecionar o ícone "Explorer" no topo da barra lateral e selecionar o arquivo na lista para abri-lo novamente.

![Reabrindo o arquivo](./images/cdd108.png?raw=true "Reabrindo o arquivo")

5. Vamos ver se obtemos resultados diferentes se fornecermos mais contexto ao Copilot. Abra o arquivo create-tables.sql no editor a partir do repositório do GitHub. (Você pode selecioná-lo e abri-lo na lista de arquivos ou usar o comando abaixo no terminal.) Role por ele e dê uma olhada rápida no conteúdo.

```
code create-tables.sql
```

6. Agora, com esse arquivo aberto, volte para o topo do arquivo dev.sql. Destaque e exclua o comentário e a consulta resultante do passo 2.

7. Digite o mesmo comentário de antes para solicitar a consulta. (Basicamente, repita o passo 2.) Veja o que o Copilot sugere desta vez. Você pode aceitar as sugestões ou alternar entre as opções. (Se você primeiro receber uma linha duplicada como a consulta, basta pressionar Enter e o Copilot deve começar a fazer sugestões mais significativas.)

```
-- defina uma instrução select para obter todos os alunos matriculados em um curso
```

8. Se tudo correr bem, esta segunda passagem deve gerar uma consulta com muitas referências mais específicas aos nomes e identificadores usados no arquivo *create-tables.sql*. (Se não, exclua o resultado e tente novamente.) Dê uma olhada na consulta e depois compare os nomes/identificadores usados com os do arquivo *create-tables.sql*. **Isso mostrará que o Copilot capta o contexto de outros arquivos disponíveis para fazer melhores sugestões.** Este é um dos princípios-chave da **Engenharia de Prompts** - fornecer o contexto certo ao Copilot para obter os melhores resultados. **Lembre-se de que o Copilot é sensível ao contexto e fornecerá melhores resultados com mais contexto.** Aproveite este momento para aprender mais sobre Engenharia de Prompts, confira [Engenharia de prompts para o GitHub Copilot](https://docs.github.com/en/copilot/using-github-copilot/prompt-engineering-for-github-copilot) na documentação do GitHub.

![Nova consulta](./images/cdd97.png?raw=true "Nova consulta")

9. Em alguns casos, podemos usar um índice separado para acelerar as operações. Vamos pedir ao Copilot para criar um novo índice com base na última consulta. Adicione a seguinte linha após a consulta atual no arquivo *dev.sql*.

```
-- escreva um índice para melhorar o desempenho da consulta
```
![índice](./images/cdd98.png?raw=true "índice")

10. Suponha que também queremos ter uma tabela para capturar a presença dos alunos. Podemos pedir ao Copilot para criar a definição da tabela para nós.

```
-- defina uma tabela para a presença dos alunos para capturar a presença por aula
```

(Aqui novamente, se você não receber uma resposta significativa do Copilot, pode precisar cutucá-lo digitando *CREATE*.) Na definição que o Copilot forneceu, pode ter adicionado um comentário para o status no mesmo formato do comentário na definição da tabela courses.registration no arquivo create-tables.sql.

![valores de status](./images/cdd99.png?raw=true "valores de status")

11. O Copilot também pode criar procedimentos armazenados. Vamos pedir para ele criar um novo procedimento armazenado para obter uma lista de alunos matriculados em um local específico. Vamos usar a interface **CMD+I**. Vá para o final do arquivo *dev.sql*, invoque o Chat do Copilot via o atalho e depois digite a linha abaixo no diálogo. Você pode escolher **Accept** ou **Discard** o resultado.

```
defina um procedimento armazenado para obter a matrícula do curso por local
```
![prompt para procedimento armazenado](./images/cdd100.png?raw=true "prompt para procedimento armazenado")

12. Podemos ser mais prescritivos com nossa definição de procedimento armazenado. Vamos adicionar uma solicitação mais complexa. Vá para a interface de Chat via o ícone na barra de ferramentas (se ainda não estiver aberta). Na janela de Chat, digite o prompt abaixo.

```
defina um procedimento armazenado para obter detalhes do instrutor associados a um local
inclua detalhes do instrutor, detalhes do local e cursos associados ao instrutor
use instructor_id como o parâmetro de entrada
```
![Definição de procedimento armazenado mais extensa](./images/cdd51.png?raw=true "Definição de procedimento armazenado mais extensa")

13. Finalmente, vamos ver o Copilot otimizar uma consulta para nós. Suponha que queremos obter todos os registros de cursos para setembro de 2023. Digite a seguinte consulta no arquivo.

```
select * from courses.registrations where year(registration_date) = 2023 and month(registration_date) = 9;
```

14. Peça ao Copilot para otimizar a consulta anterior. Você pode fazer isso destacando a consulta (certifique-se de destacar a *consulta inteira*), mude para a interface de chat separada e digite "optimize" no diálogo. Você pode Accept ou Discard a otimização sugerida depois disso.

```
optimize
```
![Otimização de uma consulta](./images/cdd116.png?raw=true "Otimização de uma consulta")

**=========== FIM DO LAB ===========**

## Lab 7 - Ensinando o Copilot sobre atualizações

**Objetivo: Neste laboratório, veremos um exemplo do que fazer quando o Copilot não tem as informações mais atualizadas**

1. Crie um novo arquivo chamado *explore.go* através da mesma abordagem que você usou para criar outros arquivos.

2. Este arquivo deve estar agora aberto em uma aba do editor. Suponha que queremos semear um gerador de números aleatórios com Go. Vamos pedir ao Copilot para escrever uma função para fazer isso. Solicite através da interface **CMD+I** usando a declaração abaixo. Depois você pode aceitar o código sugerido.

```
escreva uma função para semear um gerador de números aleatórios
```
![Pedindo ao Copilot para escrever função para semear um gerador de números aleatórios](./images/cdd117.png?raw=true "Pedindo ao Copilot para escrever função para semear um gerador de números aleatórios")

3. O Copilot provavelmente gerou código usando a função rand.Seed. O desafio é que a partir do Go 1.20, a função Seed está obsoleta. Ref: https://cs.opensource.google/go/go/+/refs/tags/go1.21.0:src/math/rand/rand.go;l=394

4. Vamos ver se o Copilot entende que isso está obsoleto. Vamos perguntar a ele através de uma consulta. Mude para a interface de chat separada e digite a consulta abaixo.

```
A função Seed está obsoleta no Go?
```
![A função Seed está obsoleta?](./images/cdd118.png?raw=true "A função Seed está obsoleta?")

5. O Copilot provavelmente respondeu com não e algumas informações sobre a função. Então, uma maneira de ajudar o Copilot a entender as atualizações de linguagem é fornecendo o contexto em nosso arquivo. Então, vamos começar novamente. Exclua o conteúdo atual no arquivo explore.go.

6. Agora, vamos fornecer ao Copilot um contexto mais direto copiando exemplos de código atualizados. Depois de excluir o bloco de código do passo 3, copie e cole o seguinte exemplo de substituição para a obsolescência do Seed no seu arquivo explore.go. Isso foi retirado de pkg.go.dev/math/rand.

```
	// Crie e semeie o gerador.
	// Normalmente, uma semente não fixa deve ser usada, como time.Now().UnixNano().
	// Usar uma semente fixa produzirá a mesma saída em cada execução.
	// r := rand.New(rand.NewSource(99))
```

7. Agora, vamos tentar a criação da função novamente. Abaixo dos comentários e código que você acabou de colar, invoque o diálogo via **CMD+I** e digite a declaração abaixo novamente.
```
escreva uma função para semear um gerador de números aleatórios
```

8. Desta vez, o código deve estar usando o mesmo formato e função NewSource que você colocou no arquivo no passo 6. Você pode simplesmente Accept a alteração. (Se você não vir uma função completa, mas apenas uma única linha, tente mudar o prompt para "escreva uma função completa para semear um gerador de números aleatórios".

![Código atualizado do gerador de números aleatórios após incluir uso atualizado](./images/cdd119.png?raw=true "Código atualizado do gerador de números aleatórios após incluir uso atualizado")

**=========== FIM DO LAB ===========**

## Lab 8 - Kubernetes, geração de YAML e garantindo que você está usando a versão mais recente

**Objetivo: Mostrar geração de YAML e conteúdo desatualizado.**

1. Crie um novo arquivo - **deployment.yaml**

```
code deployment.yaml
```

2. Abra o diálogo de Chat do Copilot via **CMD+I** e digite a seguinte solicitação.

```
escreva uma especificação para implantação no Kubernetes com 2 réplicas e imagem do busybox
adicione comando para executar nos contêineres: sleep 3600
adicione rótulo app: myapp
adicione rótulo type: front-end
```

3. Depois de alguns momentos, você deve ver a resposta com o código. Você pode simplesmente Accept isso.
![Manifesto do Kubernetes](./images/cdd120.png?raw=true "Manifesto do Kubernetes")

4. Suponha que não sabemos como executar este código. Vamos perguntar ao Copilot. Destaque o YAML gerado no arquivo deployment.yaml. Em seguida, vá para a interface de chat maior e pergunte a ele. Coloque o seguinte na interface de chat.

```
Como eu executo isso?
```

5. O Copilot deve responder com algo como o seguinte:

![Como executar a implantação](./images/cdd121.png?raw=true "Como executar a implantação")

6. Enquanto estamos na interface de chat, vamos perguntar sobre a versão mais recente do K8s. Coloque o seguinte no diálogo.

```
qual é a versão mais recente do Kubernetes?
```

7. Observe que ele identifica a versão mais recente como 1.28 a partir de outubro de 2023. Isso destaca o problema de desatualização com o LLM.

![Resposta para a versão mais recente do K8s](./images/cdd122.png?raw=true "Resposta para a versão mais recente do K8s")

No entanto, o GitHub Copilot evoluiu para perceber que o modelo atual pode não ter as informações mais recentes. Portanto, a resposta pode incluir um link para a página de lançamentos do Kubernetes: https://github.com/kubernetes/kubernetes/releases. Este é um exemplo de como o Copilot pode ajudá-lo a encontrar as informações mais atualizadas. Vá para essa página e veja qual é a versão mais recente.

8. Vamos pedir ao Copilot para gerar algum código para trabalhar com o Kubernetes através da API. Na interface de chat, digite o seguinte.

```
Como eu chamo a API do K8s para escalar uma implantação para 5 réplicas com Python?
```

9. Os resultados podem nos dizer que primeiro precisamos garantir que algo como o PIP esteja instalado. Se for o caso, não precisamos nos preocupar com isso no momento. Vá para o código gerado na saída do chat. Clique nessa área de saída e cole o código em um novo arquivo clicando nos "..." e depois na opção de menu *Insert into new file*.

![Adicionar código a um novo arquivo](./images/cdd124.png?raw=true "Adicionar código a um novo arquivo")

10. Suponha que mudamos de ideia e queremos converter este código para Go. Clique no novo arquivo e destaque o novo código. Em seguida, na interface de chat, diga para traduzir para Go. Depois, olhe na saída do chat separada e você deve ver o código Go equivalente disponível.

```
traduzir para Go
```

11. Se você olhar para a saída da interface de chat, agora deve ter o código Go equivalente disponível.

![Tradução para Go](./images/cdd125.png?raw=true "Tradução para Go")

**=========== FIM DO LAB ===========**

## Lab 9 - Explorando JavaScript, gerador de expressões regulares, geração automática de dados

**Objetivo: Mostrar geração de JavaScript e expressões regulares, geração automática de mapeamentos de rotina**

1. Crie um novo arquivo como **phone.js**

```
code phone.js
```

2. Solicite ao Copilot para criar uma função com uma expressão regular para validar um número de telefone dos EUA. Você pode usar a interface **CMD+I** e simplesmente *Accept* os resultados.
```
crie uma função para validar qualquer número de telefone global usando uma expressão regular
```
![Função Regex para validar número de telefone](./images/cdd127.png?raw=true "Função Regex para validar número de telefone")

3. Vamos dizer para ele documentar a função destacando o código, invocando **CMD+I** e **/doc**. Você pode simplesmente Accept os resultados.

![Documentação automática da função](./images/cdd128.png?raw=true "Documentação automática da função")

4. Agora vamos ver como o Copilot pode gerar alguns dados e mapeamentos para nós automaticamente. Digite o prompt abaixo na área de texto principal/separada do chat.
```
crie um mapeamento de todos os 50 estados para códigos de área onde
a chave é a abreviação do estado e o valor
é um array de códigos de área com no máximo 10
```
5. Depois de executar isso, o Copilot gerará o início de uma lista como mostrado abaixo. Passe o mouse sobre a área de saída e clique no ícone que aparece para o terminal. Clique nele para inserir o comando no terminal. Em seguida, pressione Enter.

![Geração automática de dados](./images/cdd129.png?raw=true "Geração automática de dados")

6. Você pode rolar até o final para confirmar se obteve entradas para todos os estados. Se não, você pode criar prompts adicionais para intervalos específicos de estados, alterar o número de valores para baixo, etc. Você pode então copiar esses valores para o seu arquivo, se desejar. No passado, o Chat do GitHub Copilot também pode ter adicionado a isenção de responsabilidade na parte inferior da saída de que esses valores podem não ser reais.

![Isenção de responsabilidade sobre valores reais](./images/cdd132.png?raw=true "Isenção de responsabilidade sobre valores reais")

7. Vamos verificar se temos ou não os códigos de área reais. Podemos perguntar ao Copilot se os códigos de área são os valores reais. Digite o seguinte na interface de chat.

```
Esses são os códigos de área reais ou são dados fabricados?
```
![Verificar dados de código de área](./images/pic023.png?raw=true "Verificar dados de código de área")

Este é outro exemplo de como o GitHub Copilot fornece recursos adicionais para ajudá-lo a verificar as informações mais recentes. Neste caso, ele está sugerindo que você vá para a Administração do Plano de Numeração da América do Norte (NANPA), onde você pode encontrar as informações mais atualizadas sobre códigos de área. Você pode ir para essa fonte e ver se os códigos de área gerados pelo Copilot são precisos. O Copilot evoluiu para compensar o fato de que o LLM pode não ter as informações mais atualizadas.

**=========== FIM DO LAB ===========**

## Lab 10 - Agentes e CLI

**Objetivo: Neste laboratório, praticaremos o uso de agentes do GitHub Copilot e do Copilot CLI.**

1. Agora vamos ver como o Copilot pode ajudar com tarefas usando agentes. Primeiro, vamos pedir ao Copilot para nos ajudar a fazer um commit de uma alteração. Vamos usar o arquivo *explore.go* que criamos em um laboratório anterior. Se você ainda não fez isso, certifique-se de que o arquivo esteja salvo. Você pode fazer isso por:
- Selecione o arquivo *explore.go*
- Clique no *menu de três linhas* no canto superior esquerdo.
- No menu que aparecer, selecione *Arquivo* e depois selecione *Salvar* (ou use o atalho).
2. Agora, vamos invocar o agente **@terminal** para perguntar uma pergunta comum sobre como preparar suas alterações de código. Vá para a interface de *chat* e digite o prompt abaixo. Depois disso, o comando para fazer a preparação deve aparecer na saída do chat.

```
@terminal como faço para preparar explore.go?
```
![saída da consulta](./images/cdd134.png?raw=true "saída da consulta")

3. Passe o mouse sobre a janela com os comandos nela e clique no ícone que aparece para o terminal. Clique nele para inserir o comando no terminal. Em seguida, pressione Enter.

![inserir no terminal](./images/cdd135.png?raw=true "inserir no terminal")

4. Agora vamos fazer o commit da nossa alteração através da interface e pedir ao Copilot para sugerir uma mensagem de commit para nós. Clique no ícone de controle de origem na barra lateral (#1 na figura abaixo). Seu arquivo *explore.go* deve estar selecionado. Na caixa intitulada "Mensagem" acima da *barra de commit*, clique no *ícone de brilho* no lado direito (#2 na figura abaixo).

![inserir no terminal](./images/cdd136.png?raw=true "inserir no terminal")
5. Depois disso, o Copilot deve (esperançosamente) gerar uma mensagem de commit apropriada nessa caixa. Você pode então copiar a mensagem e colá-la em um comando *git commit* no terminal. **Se você iniciou seu codespace a partir de um fork, pode pressionar Enter para concluir o commit, se desejar. Isso é opcional. Se você iniciou seu codespace através do botão de um clique, não terá permissões para fazer commit.**
```
git commit -m "<conteúdo da mensagem de commit gerada pelo Copilot vai aqui>"
```
![commit com mensagem gerada](./images/cdd137.png?raw=true "commit com mensagem gerada")

6. Agora, vamos mudar de marcha e usar o agente **@workspace** para ajudar a identificar onde usamos certas coisas em nosso código. Com o arquivo *explore.go* ainda ativo no seu editor, na interface de *chat* separada, digite o seguinte prompt:

```
Quais arquivos estão usando SQL?
```

7. Depois de executar isso, você provavelmente terá algumas informações sugeridas sobre como procurar arquivos que usam SQL no seu projeto com a funcionalidade de pesquisa do Visual Studio Code.
![resposta inicial da consulta](./images/cdd138.png?raw=true "resposta inicial da consulta")
8. Esta não é o tipo de resposta que estávamos procurando. Vamos repetir a consulta com o agente *@workspace*.
```
@workspace Quais arquivos estão usando SQL?
```
9. Depois de executar isso, você deve ver o Copilot avaliando todos os arquivos no workspace e depois retornando uma resposta mais específica e esperada.
![resposta mais específica](./images/cdd139.png?raw=true "resposta mais específica")

**=========== FIM DO LAB ===========**

## Lab 11 - GitHub Copilot CLI
1. Finalmente, vamos trabalhar com a interface de linha de comando do Copilot. O codespace já tem o GitHub CLI instalado, então só precisamos instalar a extensão do Copilot e autenticar. Digite o seguinte no terminal.

```
gh extension install github/gh-copilot
```

2. Depois disso, você pode invocar o comando de linha de comando do copilot para ver as opções disponíveis.

```
gh copilot
```
![Ajuda do Copilot CLI](./images/cdd94.png?raw=true "Ajuda do Copilot CLI")

3. Para autenticar, use o comando abaixo no terminal.

```
gh auth login --web
```

4. Siga as instruções. Você receberá um código de ativação único que deve copiar e colar no navegador quando solicitado. (Se você receber uma mensagem sobre um problema com o GITHUB_TOKEN, pode usar o comando *export GITHUB_TOKEN=* para limpá-lo.) Você precisará clicar no botão "Authorize GitHub" na próxima tela e depois confirmar seu login após isso para concluir o processo.
```
export GITHUB_TOKEN=
```
![Autenticação do Copilot CLI](./images/cdd95.png?raw=true "Autenticação do Copilot CLI")

5. Depois de autenticar, você pode tentar alguns comandos *gh copilot* como os abaixo para ver um exemplo de como o CLI funciona.

```
gh copilot explain "ps -aux"
```

```
gh copilot suggest "install terraform"
```

**=========== FIM DO LAB ===========**

## Lab 12 - Sendo específico em seus prompts

**Objetivo: Neste laboratório, começaremos com um comando simples e depois adicionaremos mais e mais especificidade e veremos como isso impacta as sugestões que recebemos.**

1. O contexto para este exercício é que queremos criar um **GitHub Actions** workflow para construir uma aplicação **.NET Core** e implantá-la no **Azure Web Apps**. Isso também demonstrará que **GitHub Copilot** vai além da programação tradicional e pode ajudá-lo com muitas outras coisas, como arquivos de workflow de CI/CD. Digite o prompt abaixo na interface de chat.

```
Crie um workflow do GitHub Actions para construir uma aplicação .NET Core e implantá-la no Azure Web Apps.
```
![Gerar um Workflow do GitHub Actions](./images/pic009.png?raw=true "Gerar um Workflow do GitHub Actions")

Reserve um tempo para analisar o **GitHub Actions** workflow resultante. Você pode ver que ele está referenciando várias Actions que vêm do **GitHub Marketplace**, que economia de tempo! Não tivemos que descobrir manualmente e procurar as várias Actions que precisam ser usadas, o GitHub Copilot fez isso por nós. Sua sugestão pode incluir uma nota importante instruindo você a gerenciar adequadamente o `AZURE_WEBAPP_PUBLISH_PROFILE`. Esta é uma forma de **segredo** que gostaríamos de gerenciar muito diligentemente para garantir que não caia nas mãos de um hacker. Podemos usar **Azure OpenID Connect** para evitar ter que gerenciar e armazenar segredos como um `AZURE_WEBAPP_PUBLISH_PROFILE`.

2. Vamos refinar o prompt para ser mais específico e ver o que acontece. Digite o prompt refinado abaixo na interface de chat.

```
Crie um workflow do GitHub Actions para construir uma aplicação .NET Core e implantá-la no Azure Web Apps.
Use "OpenID Connect" para autenticar com o Azure.
```
![Gerar um Workflow do GitHub Actions](./images/pic010.png?raw=true "Gerar um Workflow do GitHub Actions")

Agora pode haver um passo `Login to Azure` que é necessário para trabalhar com **Azure OpenID Connect**. Além disso, as notas importantes se referirão a `AZURE_CLIENT_ID`, `AZURE_TENANT_ID` e `AZURE_SUBSCRIPTION_ID`. Estes são apenas identificadores para o seu ambiente específico do Azure e não uma forma de segredo que um hacker poderia usar para acessar e alterar seu aplicativo web. Ao adicionar mais especificidade ao nosso prompt, tornamos nossa implantação mais segura.

3. Este é um ótimo começo, mas você também deve incluir verificações de qualidade em seu workflow de CI/CD, como executar testes automatizados, testes de carga, etc. Podemos usar o framework de testes **Playwright** e **Azure Load Testing** para isso. Vamos adicionar mais especificidade ao prompt. Digite o prompt refinado abaixo na interface de chat.

```
Crie um workflow do GitHub Actions para construir uma aplicação .NET Core e implantá-la no Azure Web Apps.
Use "OpenID Connect" para autenticar com o Azure.
Depois que o aplicativo for implantado, execute um conjunto de testes funcionais usando o framework Playwright
e depois, execute um conjunto de testes de carga usando o Azure Load Tests.
```
Dê uma olhada no novo workflow e nas notas relacionadas. Ao adicionar mais e mais especificidade ao nosso prompt, conseguimos um **GitHub Actions** workflow mais abrangente e não tivemos que interromper nosso fluxo, sair do IDE e ir ao GitHub Marketplace para descobrir quais Actions usar.

Agora que temos esse workflow, podemos pedir ao GitHub Copilot para inserir o workflow sugerido em um novo arquivo em nosso workspace. Para fazer isso, você deve passar o mouse sobre o topo da sugestão, clicar nos `...` e selecionar `Insert into New File`. Você também pode querer copiar as notas relacionadas dessa janela de chat e colá-las em sua ferramenta de planejamento e rastreamento (por exemplo, **GitHub Issues and Projects**, Jira, Azure Boards, etc.).

![Gerar um Workflow do GitHub Actions](./images/pic011.png?raw=true "Gerar um Workflow do GitHub Actions")

Os principais pontos deste laboratório são que você pode iterar através do **GitHub Copilot Chat** adicionando mais e mais especificidade para acabar com uma sugestão muito abrangente. Portanto, ao criar prompts, certifique-se de pensar sobre quais especificidades você deve adicionar para ajudar a garantir que o **GitHub Copilot** forneça sugestões que atendam a todos os seus requisitos de escalabilidade, manutenção, robustez, etc. Além disso, **GitHub Copilot** pode ser usado para gerar muito mais do que apenas "código" tradicional. Onde mais você gostaria de aproveitar o **GitHub Copilot**? Criando arquivos de Infraestrutura como Código, como arquivos Terraform? Escrevendo scripts PowerShell? **GitHub Copilot** é seu Programador Parceiro de IA para quase tudo.

**=========== FIM DO LAB ===========**

## Lab 13 - Fique no fluxo com o GitHub Copilot

**Objetivo: Neste laboratório, mostraremos como você pode usar o GitHub Copilot Chat para obter respostas a perguntas relacionadas à programação sem sair do seu editor.**

1. Use a interface de chat para fazer uma pergunta sobre um tópico de programação. Por exemplo, você pode perguntar sobre a versão mais recente de uma linguagem de programação, como usar uma função específica ou como resolver um problema específico. Digite a pergunta abaixo na interface de chat.

```
Qual é a versão LTS mais recente do Node.js?
```
![Use o Copilot para fazer perguntas de programação](./images/pic002.png?raw=true "Use o Copilot para fazer perguntas de programação")

A resposta é baseada nas informações disponíveis para o Copilot no momento em que os modelos foram treinados. Pode haver um link para uma fonte online para as informações mais atuais, por exemplo, `site oficial do Node.js`.

[A partir de junho de 2024, há um novo recurso do **GitHub Copilot Enterprise**](https://github.blog/changelog/2024-06-14-new-copilot-enterprise-features-in-vs-code-preview/): **GitHub Copilot Enterprise** agora pode pesquisar no Bing dentro das conversas de chat no VS Code para responder perguntas e encontrar informações fora de seu conhecimento geral ou de seu código. Para obter respostas enriquecidas com resultados de pesquisa do Bing, comece sua mensagem com `@github`. O Copilot decidirá inteligentemente quando usar o Bing. **Este recurso está ATUALMENTE DISPONÍVEL APENAS no GitHub Copilot Enterprise**, então o apresentador mostrará como isso funciona, pois não está disponível no **GitHub Copilot Individual**.

2. Vamos tentar usar `@github` para obter uma resposta baseada em uma pesquisa no Bing. Digite a pergunta abaixo na interface de chat.

```
@github Qual é a versão LTS mais recente do Node.js?
```
![Use o Bing com o Copilot para fazer perguntas de programação](./images/pic003.png?raw=true "Use o Bing com o Copilot para fazer perguntas de programação")

Esta resposta é enriquecida com resultados de pesquisa do Bing. Você pode usar este recurso para obter respostas a perguntas que não são cobertas pelo conhecimento geral do Copilot ou pelo seu código.

3. Vamos ver se podemos usar `@github` para aprender sobre as vantagens de usar o **GitHub Copilot**. Digite a pergunta abaixo na interface de chat.

```
@github Por que o GitHub Copilot é melhor e mais seguro de usar do que solicitar ao ChatGPT e copiar/colar o código de volta no meu IDE?
```
A resposta ajuda você a entender por que o GitHub Copilot é melhor e **mais seguro** de usar do que solicitar ao ChatGPT e copiar/colar o código de volta no seu IDE?

4. Aprenda como começar com o **Azure OpenAI Service**

Você pode aproveitar o **Azure OpenAI Service** para construir seu próprio copiloto e aplicativos de IA generativa. Mas, como começar? Vamos perguntar ao GitHub Copilot. Digite a pergunta abaixo na interface de chat, **certifique-se de substituir `[language X]` pela linguagem que você provavelmente usará, por exemplo, `JavaScript` ou `Python` ou `Java`, etc.**

```
@github Usamos [language X] para desenvolvimento de aplicativos. Como eu começaria com o Azure OpenAI?
```
![Visual para o passo 1](./images/pic006.png?raw=true "Visual para o passo 1")

Isso fornece uma riqueza de informações. Para salvar a resposta, clique com o botão direito em qualquer lugar da resposta e selecione `Copiar`. Agora você pode colar a resposta em algum lugar que possa consultar mais tarde, como um **GitHub Issue** ou uma **postagem de Discussão do GitHub**.

5. Embora possamos usar `@github` para obter respostas a perguntas de programação, não podemos usar o GitHub Copilot Chat para fazer perguntas gerais. Por exemplo, você não pode perguntar sobre o clima ou os últimos resultados esportivos. Digite a pergunta abaixo na interface de chat.

```
@github Quem ganhou o Super Bowl em 1986?
```
![O GitHub Copilot é apenas para programação](./images/pic004.png?raw=true "O GitHub Copilot é apenas para programação")

Tudo bem. Todo mundo sabe que [os Chicago Bears ganharam o Super Bowl XX em 1986](https://www.chicagotribune.com/2016/01/26/chicago-bears-win-super-bowl-xx/). 😉

![Chicago Bears ganham o Super Bowl XX](https://www.chicagotribune.com/wp-content/uploads/migration/2016/01/26/QP6TV57DS5ABJDLYCFXR6BGJEM.jpg?w=1200 "Chicago Bears ganham o Super Bowl XX")

**=========== FIM DO LAB ===========**

## Conclusão e próximos passos

**O GitHub Copilot pode ser usado com quase qualquer linguagem!**
Como você viu neste laboratório, você pode usar o GitHub Copilot para gerar código em quase qualquer linguagem. Você também pode usá-lo para gerar Markdown. **GitHub Copilot** foi usado para gerar o conteúdo deste guia de laboratório.

### Confira esses recursos para se aprofundar e aprender mais
Se você completou todos os laboratórios e ainda há tempo restante na sessão de hoje, você pode conferir os recursos em [**GitHub-Copilot-Resources.md**](https://github.com/DaveOps30/copilot-hands-on/blob/main/GitHub-Copilot-Resources.md).

Esta lista de recursos foi cuidadosamente selecionada para ajudá-lo a aprender mais sobre o GitHub Copilot, como usá-lo de forma eficaz, o que está por vir no futuro, o que os clientes do GitHub estão dizendo e mais. Há até uma playlist no YouTube que inclui os vídeos mais recentes da equipe de Relações com Desenvolvedores do GitHub e outros do GitHub.

Adicione https://github.com/DaveOps30/copilot-hands-on/blob/main/GitHub-Copilot-Resources.md aos seus favoritos do navegador para fácil acesso a esses recursos a qualquer momento no futuro.

### Quer aprender mais? Confira o "Microsoft Learn"
[Microsoft Learn](https://learn.microsoft.com/) tem uma infinidade de caminhos de aprendizado. Se você ainda tem tempo nesta sessão e/ou deseja continuar aprendendo mais sobre o **GitHub Copilot**, confira o [**GitHub Copilot Fundamentals - Understand the AI pair programmer** caminho de aprendizado](https://learn.microsoft.com/training/paths/copilot/). Aqui estão alguns módulos que servem como ótimos seguimentos para este laboratório:
- [Introdução à engenharia de prompts com o GitHub Copilot](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot/) - Descubra o essencial para criar prompts eficazes com o GitHub Copilot. Descubra técnicas para transformar seus comentários de código em código preciso e acionável, aprimorando seu fluxo de trabalho de desenvolvimento. (26 min)
- [Introdução ao GitHub Copilot for Business](https://learn.microsoft.com/training/modules/introduction-to-github-copilot-for-business/) - Aprenda sobre a diferença entre **GitHub Copilot for Business** versus **GitHub Copilot for Individuals**, casos de uso específicos e histórias de clientes para o GitHub Copilot for Business, e como habilitá-lo. (23 min)
- [Introdução ao GitHub Copilot Enterprise](https://learn.microsoft.com/training/modules/introduction-to-github-copilot-enterprise/) - Aprenda sobre as diferenças entre **GitHub Copilot for Enterprise**, for Business e for Individuals. Examine casos de uso específicos, incluindo como habilitar e usar o **GitHub Copilot Enterprise**. (17 min)

Adicione **https://learn.microsoft.com/** aos seus favoritos para que você possa explorar outros **Caminhos de Aprendizado** no futuro, como [**Desenvolver soluções de IA generativa com o Azure OpenAI Service**](https://learn.microsoft.com/training/paths/develop-ai-solutions-azure-openai/)

### Por favor, deixe-nos saber o que você acha do GitHub Copilot e deste workshop
<!-- Instruir os participantes do laboratório a responderem as perguntas da pesquisa encontradas aqui: https://github.com/DaveOps30/copilot-hands-on/discussions -->
<!-- Referenciar especificamente as perguntas da pesquisa "Workshop Survey". Além disso, mencionar que eles podem usar o "Workshop Feedback & Suggestions" para feedback geral e/ou sugestões. -->
Adoraríamos ouvir seus pensamentos sobre o GitHub Copilot e este workshop.
- Por favor, reserve um momento para responder às perguntas da pesquisa no [**Workshop Survey**](https://github.com/DaveOps30/copilot-hands-on/discussions/categories/workshop-survey).
  - Para cada uma das duas perguntas, basta selecionar sua resposta e clicar no botão "Vote".
  - Sinta-se à vontade para deixar um comentário para nos informar o que você realmente gostou e/ou o que poderíamos fazer de diferente para tornar este workshop mais valioso no futuro.
- Se você tiver algum feedback ou sugestões de melhoria, por favor, nos avise na categoria de discussão [`Workshop Feedback & Suggestions`](https://github.com/DaveOps30/copilot-hands-on/discussions/categories/workshop-feedback-suggestions).

<p align="center">
**OBRIGADO!**
</p>
