# Implementação do Algoritmo para Caminho Hamiltoniano
## Descrição Geral

Este projeto tem como objetivo implementar um algoritmo capaz de encontrar um Caminho Hamiltoniano em um grafo orientado ou não orientado.
Um Caminho Hamiltoniano é uma sequência de vértices em que cada vértice do grafo é visitado exatamente uma vez, sem repetições.

## Estrutura e Lógica do Algoritmo

A implementação é baseada em uma abordagem de backtracking, utilizada para explorar todas as possibilidades de caminhos até encontrar uma solução válida.

A seguir, está o detalhamento da lógica utilizada:

1 - Representação do Grafo
O grafo é modelado por meio de uma matriz de adjacência, encapsulada em uma classe chamada Grafo.

2 - Adição de Arestas
O método adicionar_aresta é responsável por incluir conexões entre dois vértices, atualizando a matriz de adjacência.

3 - Verificação de Segurança (eh_seguro)
Antes de inserir um vértice no caminho, o algoritmo verifica se:

Existe uma aresta que conecta o último vértice do caminho ao novo vértice candidato.

O vértice ainda não foi visitado anteriormente no caminho.

4 - Backtracking (caminho_hamiltoniano_util)
Esse método é o núcleo do algoritmo:

Caso base: quando todos os vértices já foram incluídos no caminho, temos uma solução válida.

Passos recursivos: para cada vértice possível, o algoritmo testa se é seguro incluí-lo; se for, ele avança recursivamente.

Caso o caminho não leve a uma solução, o algoritmo retrocede (backtrack) e tenta outra alternativa.

5 - Execução Principal (encontrar_caminho_hamiltoniano)
O processo é iniciado a partir do vértice 0, e o algoritmo tenta construir o caminho completo a partir dele.

## Como Executar o Projeto
### Requisitos

Python 3.x instalado.

Bibliotecas necessárias:

pip install networkx matplotlib

### Execução

Clonar o repositório:

git clone https://github.com/diogotorres13/atividade_3_fpaa.git


### Acessar o diretório:

cd atividade_3_fpaa


### Executar o programa principal:

python main.py


### Visualizar o grafo (opcional):

python view.py

## Relatório Técnico
### Complexidade Computacional

O problema do Caminho Hamiltoniano pertence à classe NP-Completo, o que implica:

Classe NP: uma solução pode ser verificada em tempo polinomial.

NP-Difícil: qualquer problema da classe NP pode ser reduzido a ele em tempo polinomial.

Não pertence à classe P: não há algoritmo conhecido que o resolva em tempo polinomial.

A relação com o Problema do Caixeiro Viajante (TSP) é direta — o TSP é uma extensão do Caminho Hamiltoniano que busca minimizar o custo total do percurso.

### Complexidade Assintótica de Tempo

O algoritmo possui complexidade de O(n!), onde n é o número de vértices do grafo.

Isso ocorre porque:

Em cada posição do caminho, o algoritmo tenta incluir todos os vértices ainda não visitados.

No pior caso, todas as permutações possíveis dos vértices são exploradas.

Cada chamada recursiva pode gerar até n - 1 novas chamadas.

### Aplicação do Teorema Mestre

O Teorema Mestre não é aplicável diretamente, pois o algoritmo não segue a forma geral de recorrência
T(n) = aT(n/b) + f(n).

As razões são:

O número de subproblemas não é constante.

Os subproblemas não têm tamanhos iguais.

A divisão do problema não ocorre de forma balanceada.

## Análise de Casos

### Pior caso: O(n!)
Quando o algoritmo precisa explorar todas as permutações dos vértices.
→ Tempo de execução cresce exponencialmente.

### Caso médio: O(n!)
Apesar de, ocasionalmente, encontrar caminhos mais rapidamente, a média de execução continua sendo fatorial.

### Melhor caso: O(n)
Quando o primeiro caminho testado já é Hamiltoniano.
→ Mesmo assim, o algoritmo é ineficiente para grafos grandes.

## Visualização do Grafo

O projeto inclui uma ferramenta de visualização gráfica construída com NetworkX e Matplotlib.

A visualização exibe:

Vértices numerados;

Arestas em azul;

Caminho Hamiltoniano destacado em vermelho, quando encontrado.
