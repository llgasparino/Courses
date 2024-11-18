# Funções Hash criptográficas

```plaintext
Uma função hash mapeia uma mensagem de entrada de tamanho variável em um bloco de dados de tamanho fixo, denominado de código hash. O Hash também é conhecido como checksum. O termo checksum é bastante utilizado para se referir ao código usado para verificar a integridade de uma mensagem transmitida ou que foi armazenada em algum meio por determinado tempo. 

Diferente dos algoritmos de criptografia convencional, o algoritmo de uma função hash não é reversível, ou seja, você não consegue retornar ao valor original. As funções hashes fornecem a garantia de que a mudança de qualquer bit na mensagem produzirá um código hash diferente. 

A função hash destinada às aplicações de segurança é denominada como função hash criptográfica. O algoritmo de uma função hash criptográfica estabelece dois princípios:  

A propriedade de mão única.  

A propriedade livre de colisão.
```
## Autenticação de mensagem
```
As funções hash criptográfica podem ser utilizadas para implementar os serviços de autenticação de mensagens. O mecanismo de autenticação de mensagens permite verificar a integridade de determinada mensagem. Este mecanismo é utilizado para garantir que uma mensagem transmitida não foi modificada, ou seja, não houve inserção ou exclusão de algum conteúdo da mensagem. Adicionalmente, o mecanismo de autenticação pode ser utilizado para fornecer garantia que a identidade de um emissor é válida. Ao utilizar uma função hash criptográfica para realizar autenticação de mensagem o valor decorrente deste processo é denominado resumo de mensagem. 
```

## Requisitos de Segurança das Funções Hash Criptográficas
Existem ao todo basicamente sete requisitos que devem ser observados na implementação de funções Hash criptográficas, seguem dispostos abaixo: 
1. Tamanho de entrada variável
2. Tamanho de saída fixo
3. Eficiência
4. Propriedade de mão única
5. Resistência à colisão fraca 
6. Resistência à colisão forte
7. Pseudoaleatoriedade 
O paradoxo do aniversário afirma que dado um grupo de 23 sujeitos selecionados aleatoriamente, a chance de dois desses sujeitos terem a mesma data de aniversário é de mais de 50%. Ainda, estendendo este paradoxo, dado 57 ou mais sujeitos, a probabilidade chega a ser maior do que 99%, contudo, não pode ser considerado exatamente 100%, exceto que haja no mínimo 367 pessoas. Este tipo de ataque pode ser utilizado para explorar a comunicação entre duas ou mais partes. Onde o ataque depende da maior probabilidade de colisão localizadas entre as tentativas de ataque aleatório e a quantidade fixa de permutações. 

- Quais os dois princípios básicos de uma função hash criptográfica?
> Propriedade de mão única e propriedade livre de colisão
- O que é o checksum e para que é utilizado?
>checksum é um hash baseado no tamanho de bits de um arquivo muito utilizado para verificar integridade do mesmo.
- Explique o conceito da propriedade mão única estabelecidas em funções hash.
> O conceito se baseia que, seja fácil gerar um hash de uma palavra ou texto porém seja impossível fazer o hash voltar a ser a palavra ou o texto novamente.
- Cite algumas aplicações de uso das funções hash criptográficas, descreva como são utilizadas.
> SSL TLS do protocolo web, hash nos commits do git para identificadores únicos, Para identificar partições em HDs
- O que é uma colisão em função hash criptográfica?
> Quando dois hashes com mensagens diferentes possui o mesmo hash de saída.
- Cite os requisitos que devem ser observados para implementação de função hash criptográfica.
> Tamanho de entrada variável, tamanho de saída fixo, ser rápido, não poder ser revertido, ter uma forte resistencia a colisões, e ser pseudoaleatório
- Descreva qual a principal diferença entre resistência à colisão fraca e a resistência à colisão forte.
>A resistência a colisão fraca significa que duas mensagens diferentes não teram a mesma saída e a resistência a colisão forte significa que possui um par de chaves no começo e no final de cada ponta de comunicação 
- Porque o algoritmo MD5 é considerado uma função hash criptográfica vulnerável?
>Porque o algoritimo já foi explorado e foi descoberto as pseudocolisões, sendo assim mais acessível e mais fácil de decifrar o hash
- Porque o algoritmo MD6 não foi adotado como padrão SHA-3?
>
- Explique como o paradoxo do aniversário pode ser utilizado para efetuar ataques em funções hash criptográficas.
>
- Qual a diferença entre o algoritmo SHA-0 e SHA-1?
>
- Quais os algoritmos que compõe o SHA-2?
>