Funciona com **log2 n** etapas  e uma pesquisa simples é **n** etapas

---
Logaritmos 
Você pode não se lembrar de logaritmos, mas provavelmente lembra-se de como calcular exponenciais.
A expressão log 10 100 basicamente diz: **“Quantos 10s conseguimos multiplicar para chegar a 100?”**. 
A resposta é 2: 10 × 10. Então, log 10 100 = 2.
Logaritmos são o oposto de exponenciais. Neste livro, quando falamos sobre a notação Big O (explicada daqui a pouco), levamos em conta que log sempre significa log2 . Quando você procura um elemento usando a pesquisa simples, no pior dos casos, terá de analisar elemento por elemento, passando por todos. Se for uma lista de oito elementos, precisaria checar no máximo oito números. Na pesquisa binária, precisa vericar log n elementos para o pior dos casos. Para uma lista de oito elementos, log 8 == 3, porque 2^3 == 8. Então, para uma lista de oito números, precisaria passar por, no máximo, três tentativas. Para uma lista de 1.024 elementos, log 1.024 == 10, porque 2^4 == 1.024. Logo, para uma lista de 1.024 números, precisaria veri  car no máximo dez deles.

>A pesquisa binária só funciona quando a sua lista está ordenada. Por exemplo, os nomes em uma agenda telefônica estão em ordem alfabética, então você pode utilizar a pesquisa binária para procurar um nome. O que aconteceria se a lista não estivesse ordenada?

```python 
    baixo = 0 
    alto = len(lista) - 1
    
    while baixo <=alto:
        meio = (baixo + alto / 2)
        chute = lista[meio]
        if chute == item:
            return meio
        if chute > item:
            alto = meio - 1 
        else: 
            baixo = meio + 1
    return None
```
EXERCÍCIOS
1.1 Suponha que você tenha uma lista com 128 nomes e esteja fazendo uma pesquisa binária. Qual seria o número máximo de etapas que você levaria para encontrar o nome desejado?
8
1.2 Suponha que você duplique o tamanho da lista. Qual seria o número
máximo de etapas agora?
9
(Isso faz referência ao log2^N == 8)

