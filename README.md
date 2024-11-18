# Soma Paralela e Serial em C++ com OpenMP

**Autor**: Yago Phellipe Matos Lopes  
**Curso**: Ciência da Computação  

---

## Sobre o Projeto

Este projeto implementa o cálculo da soma de uma lista de números inteiros usando duas abordagens: **serial** e **paralela**. A solução foi otimizada para evitar overheads desnecessários, como dividir a lista em subgrupos (pares e ímpares) e realizar cálculos separados. Agora, a soma é realizada diretamente sobre a lista inteira, tanto na versão serial quanto na paralela.

---

## Funcionalidades

- **Soma Serial**: 
  - Realiza a soma de todos os elementos de uma lista de forma sequencial.
  - Utiliza um único loop simples.

- **Soma Paralela**:
  - Utiliza a biblioteca OpenMP para dividir a carga de trabalho entre múltiplos threads.
  - Implementa `#pragma omp parallel for` com uma redução (`reduction`) para somar os valores de forma eficiente e segura em paralelo.
  - Permite testar o desempenho com diferentes números de threads.

---

## Como Funciona?

1. **Inicialização da Lista**:
   - A lista é preenchida com números aleatórios entre 0 e 999.
   - O tamanho da lista é configurado para **100 milhões de elementos**, ideal para testes de desempenho.

2. **Cálculo da Soma**:
   - **Serial**:
     - Um único loop percorre a lista e acumula a soma em uma variável.
   - **Paralelo**:
     - A lista é dividida em blocos que são processados simultaneamente por diferentes threads.
     - A soma é feita com uma redução para garantir que o valor final seja correto.

3. **Validação**:
   - Após calcular as somas serial e paralela, os resultados são comparados para garantir que ambos produzam o mesmo valor.

4. **Medição de Desempenho**:
   - O tempo de execução é medido para ambas as abordagens.
   - A soma paralela é testada com diferentes números de threads (2, 4 e 8) para observar o impacto do paralelismo no desempenho.

---
