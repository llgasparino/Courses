```python
def buscaMenor(arr):
    menor = arr[0] ❶
    menor_indice = 0 ❷
    for i in range(1, len(arr)):
        if arr[i] < menor:
            menor = arr[i]
            menor_indice = i
    return menor_indice

def ordenacaoporSelecao(arr): ❶
    novoArr = []
    for i in range(len(arr)):
        menor = buscaMenor(arr) ❷
        novoArr.append(arr.pop(menor))
return novoArr
print ordenacaoporSelecao([5, 3, 6, 2, 10])
```
• A memória do seu computador é como um conjunto gigante de gavetas.
• Quando se quer armazenar múltiplos elementos, usa-se um array ou uma
lista.
• No array, todos os elementos são armazenados um ao lado do outro.
• Na lista, os elementos estão espalhados e um elemento armazena o
endereço do próximo elemento.
• Arrays permitem leituras rápidas.
• Listas encadeadas permitem rápidas inserções e eliminações.
• Todos os elementos de um array devem ser do mesmo tipo (todos ints,
todos doubles, e assim por diante).