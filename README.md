## Implementação de Padrões de Projeto - BCC3004

Aluno: Josué Modesto da Costa 
RA: 2304376 

Para a explicação e descrição dos padrões de projeto escolhidos e implementados foi utilizado os conteúdos do site: {https://refactoring.guru/pt-br/design-patterns}

Também foi utilizado o ChatGpt para correção e melhoria dos textos, e para pulir as ideias de exemplos. 

# 1 - Padrão Comportamental 

O padrão comportametal escolhido foi o Observer, padrão que permite que você defina um mecanismo de assinatura para notificar múltiplos objetos sobre quaisquer eventos que aconteçam com o objeto que eles estão observando. Com isso, apenas os objetos que possuem uma assinatura (inscrição) recebem as atualizações, enquanto os demais não são afetados. Esse padrão facilita a comunicação entre classes e diminui o acoplamento do sistema, tornando o código mais organizado e flexível.

# Problema e Solução
O problema proposto consiste em uma classe Nike, que atua como objeto observado (Subject). A empresa possui vendedores premium e vendedores comuns, que podem se cadastrar para receber notificações sobre novos lançamentos de produtos, alguns produtos são somente para vendedores premium. Para resolver esse problema, foi utilizado o padrão Observer. Os vendedores são registrados na Nike e passam a receber atualizações sempre que um novo produto é lançado. Os vendedores premium recebem notificações de todos os lançamentos, enquanto os vendedores comuns recebem notificações apenas de produtos com código maior ou igual a 5.

Além disso, um vendedor pode cancelar sua inscrição por meio do método detach(), deixando de receber futuras notificações. Dessa forma, o padrão Observer permite que a Nike notifique automaticamente os vendedores interessados, reduzindo o acoplamento entre as classes e facilitando a manutenção do sistema.

# Implementação 

A implementação do padrão de projeto Observer foi realizada em TypeScript.

Para auxiliar no entendimento e na implementação do padrão Observer, foi utilizado como base o exemplo disponibilizado pelo Refactoring Guru:
https://refactoring.guru/pt-br/design-patterns/observer/typescript/example

# Execução 

Para executar o código implementado, acesse o diretório comportamental e execute o comando:

npx tsx observer.ts

A saída esperada é semelhante à seguinte:

Nike: Novo vendedor cadastrado.
Nike: Novo vendedor cadastrado.

Nike: Lançando um novo produto.
Nike: Novo produto disponível. Código: 1
Nike: Notificando vendedores...
Vendedor Premium: Recebeu o lançamento.

Nike: Lançando um novo produto.
Nike: Novo produto disponível. Código: 6
Nike: Notificando vendedores...
Vendedor Premium: Recebeu o lançamento.
Vendedor Comum: Recebeu a notificação do produto.
Nike: Vendedor removido.

Nike: Lançando um novo produto.
Nike: Novo produto disponível. Código: 6
Nike: Notificando vendedores...
Vendedor Premium: Recebeu o lançamento.

# Conclusão 
Como visto na execução do programa, o vendedor premium recebe notificações de todos os lançamentos realizados pela Nike. Já o vendedor comum recebe notificações apenas dos produtos com código maior ou igual a 5. Também foi demonstrado o uso do método detach(), que remove um vendedor da lista de observadores. Após sua remoção, o vendedor comum deixa de receber notificações sobre novos produtos.
Dessa forma, foi possível demonstrar o funcionamento do padrão Observer, no qual os vendedores são notificados automaticamente quando a Nike lança um novo produto.

# 2 Padrão - Criacional

O padrão criacional escolhido foi o Factory Method, que é um padrão de projeto que fornece uma interface para criar objetos em uma superclasse, mas permite que as subclasses alterem o tipo de objetos que serão criados.