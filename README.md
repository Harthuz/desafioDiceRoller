## Documentação do Aplicativo Dice Roller

### Tela Principal (MainActivity)

A classe `MainActivity` é a classe principal do aplicativo. Ela infla a composição da tela principal (`DiceRollerApp`) usando o tema `DiceRollerTheme`.

### Compose DiceRollerApp

Este Compose representa a tela principal do aplicativo. Ele exibe um `Surface` como fundo e posiciona o `DiceWithButtonAndImage` no centro da tela.

### Compose DiceWithButtonAndImage

Este Compose representa a parte principal da tela do aplicativo, onde o dado e o botão de rolar ficam visíveis.

#### Atributos:

- `modifier`: Modificador para definir o layout do Compose (preenchimento da tela e centralizado).
- `result`: Estado mutável que armazena o valor do dado (1-6).
- `input`: Estado mutável que armazena o número digitado pelo usuário (texto).
- `verificado`: Estado mutável que armazena a mensagem de verificação (acertou/errou/número inválido).
- `context`: Recupera o contexto da Activity atual.
- `imageResource`: Define o recurso de imagem do dado baseado no valor de `result`.

#### Elementos:

- `Image`: Exibe a imagem do dado de acordo com o valor de `result`.
- `Button`: Botão para rolar o dado.
    - Ao clicar no botão:
        - `result` é atualizado com um número aleatório entre 1 e 6.
        - A função `verificacao` é chamada para checar o acerto e atualizar `verificado`.
        - Uma mensagem Toast é exibida usando o `context` e o valor de `verificado`.
- `OutlinedTextField`: Campo de texto para o usuário digitar um número.
    - `value`: Valor atual do campo (`input`).
    - `onValueChange`: Função para atualizar o valor do campo (`input`) conforme o usuário digita.
    - `label`: Texto de instrução para o campo ("Digite um número").
    - `keyboardOptions`: Configura o teclado para entrada numérica.

### Função `verificacao`

Esta função verifica o número digitado pelo usuário (`inputB`) e o resultado do dado (`resultB`). Ela retorna uma mensagem de acordo com o seguinte:

- Se `inputB` estiver entre 1 e 6:
    - Se `inputB` for igual a `resultB`: "Você acertou! :)"
    - Se `inputB` for diferente de `resultB`: "Você errou :("
- Caso contrário: "Por favor, digite um número entre 1 e 6."
