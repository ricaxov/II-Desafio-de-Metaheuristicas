# Análise de Resultados

## 1. Descrição do Problema

- O Problema de Empacotamento Unidimensional (1D Bin-Packing) é um clássico problema de otimização combinatória que se concentra em organizar um conjunto de itens em caixas de forma eficiente.

- Nesse problema, são dados um conjunto de $N$ itens. Cada item $i$ possui um peso $W_i$, indicando que esse item consome $W_i$ unidades da capacidade de uma caixa. Também é dado um valor $C$, indicando a capacidade máxima de uma caixa.

- O objetivo é empacotar todos os itens nas caixas de forma que o número total de caixas utilizadas seja o menor possível.

<p align="center">
  <img src="https://github.com/user-attachments/assets/1406f897-3bd5-4822-8e70-e228648f9900" alt="Conjunto de Itens" width="300"/>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/a59e4492-0385-4152-ad9a-d968d50022d8" alt="Solução Ótima" width="500"/>
</p>

## 2. Objetivos dos Experimentos

Os objetivos dos experimentos realizados são:

- Avaliar a eficiência dos Genetic Algorithm (GA), Cuckoo Search (CS), e uma variação do Simulated Annealing (SA) com método de bisecção.
- Testar diferentes parâmetros para cada um dos algoritmos e analisar seus impactos.
- Verificar a convergência da solução de cada algoritmo.
- Avaliar os trade-offs entre o tempo de execução e a qualidade da solução obtida.

## 3. Metodologia dos Experimentos

### Configurações dos Algoritmos

#### Cuckoo Search
- **Parâmetros Utilizados:**
  - Tamanho da população (n).
  - Taxa de abandono dos ninhos (pa).
  - Passo de salto de Lévy (α).
  - Número de gerações (G).
  - Distribuição de Lévy.
  - Limites de busca.
- **Justificativa das Escolhas:**
  - Explicar os critérios para a definição desses parâmetros com base em estudos anteriores ou experimentação preliminar.

#### Genetic Algorithm
- **Parâmetros Utilizados:**
  - **Tamanho da população**
  - **Taxas de cruzamento e mutação**
  - **Número de gerações**:

- **Justificativa das Escolhas:**
  - As escolhas dos parâmetros são baseadas em referências da literatura e experimentos iniciais. Por exemplo, um **tamanho de população** maior pode explorar melhor o espaço de busca, enquanto **taxas de cruzamento** mais altas tendem a favorecer a intensificação (explorar boas soluções) e **taxas de mutação** mais baixas garantem que o algoritmo não se distancie demais das soluções boas. O **número de gerações** foi ajustado com base nos testes iniciais, equilibrando qualidade de solução e tempo de execução.

#### Simulated Annealing + Bisecção
- **Parâmetros Utilizados:**
  - **Temperatura inicial**
  - **Taxa de resfriamento**
  - **Critério de parada**
  - **Taxa de mutação**
  - **Método de bisecção**

- **Justificativa das Escolhas:**
  - O **Simulated Annealing** funciona com base no princípio do resfriamento gradual para escapar de mínimos locais. A escolha dos parâmetros foi guiada pela necessidade de **exploração** no início (temperatura alta), seguida de **intensificação** na busca (temperatura baixa). O uso da **bisecção** melhora a eficiência, ajustando o processo de busca. As taxas de cruzamento e mutação são menores, porque o foco do SA é ajustar pequenas variações de forma progressiva, ao contrário do GA, que depende de uma diversidade maior de soluções.

### Instâncias de Teste

- **Descrição das Instâncias:**
  - As instancias usadas eu nao sei quais foram ainda
- **Detalhes dos Dados:**
  - Os dados foram obtidos do dataset [BPPLIB](https://site.unibo.it/operations-research/en/research/bpplib-a-bin-packing-problem-library).

### Ambiente de Teste

- **Hardware:**
  - 8 GiB RAM
  - Sistema Operacional Windows 11
  - AMD Ryzen 3 7320U com Radeon Graphics, 2401 Mhz, 4 Núcleo(s), 8 Processador(es) Lógico(s)

- **Software:**
  - Visual Studio Code

## 4. Apresentação dos Resultados

### Dados Brutos

- **Tabelas de Resultados:**
  - Apresentar os dados de forma clara e organizada.
- **Gráficos:**
  - Utilizar gráficos para ilustrar os dados de forma visual, facilitando a análise comparativa.

### Estatísticas

- **Métricas Calculadas:**
  - Média dos resultados obtidos.
  - Desvio padrão.
  - Intervalos de confiança.

## 5. Análise Comparativa

### Comparação com Outras Metaheurísticas

- **Algoritmos Comparados:**
  - Comparar o desempenho do GA, Cuckoo e SA+Bisecção.
- **Discussão dos Resultados:**
  - Analisar as semelhanças e diferenças nos resultados obtidos pelos diferentes algoritmos.

### Comparação com Soluções Ótimas ou Heurísticas

- **Soluções de Referência:**
  - Apresentar soluções ótimas conhecidas.
- **Avaliação da Proximidade:**
  - Discutir quão próximo cada algoritmo se aproxima da solução ótima.

## 6. Discussão dos Resultados

### Interpretação

- **Significado dos Resultados:**
  - Explicar o que os resultados indicam sobre o desempenho dos algoritmos.
- **Padrões Observados:**
  - Identificar padrões consistentes nas execuções.

### Limitações

- **Desafios Enfrentados:**
  - Citar dificuldades como problemas de escala e tempo computacional elevado.
- **Qualidade das Soluções:**
  - Avaliar possíveis limitações na qualidade das soluções geradas.

## 7. Comparação com Objetivos Iniciais

### Alcançou os Objetivos?

- **Avaliação:**
  - Avaliar se os objetivos dos experimentos foram atingidos.
- **Justificativas:**
  - Explicar por que os objetivos foram ou não alcançados.

### Surpresas ou Descobertas

- **Resultados Inesperados:**
  - Mencionar achados inesperados e possíveis insights decorrentes.

## 8. Sugestões para Trabalhos Futuros

### Melhorias Potenciais

- **Otimizações:**
  - Sugerir possíveis melhorias nos algoritmos ou na metodologia.
- **Novos Experimentos:**
  - Propor experimentos adicionais que poderiam ser explorados.

### Aplicações

- **Outros Contextos:**
  - Discutir possíveis aplicações dos algoritmos em outros problemas.
- **Expansão do Trabalho:**
  - Apontar direções futuras para expandir a pesquisa.

## 9. Conclusão

### Síntese dos Achados

- **Resumo:**
  - Resumir os principais resultados e conclusões obtidas.
- **Implicações:**
  - Discutir a importância prática e teórica dos resultados.

### Impacto

- **Contribuição para a Área:**
  - Explicar como o trabalho contribui para o campo de metaheurísticas.
- **Relevância Prática:**
  - Comentar sobre a utilidade prática dos resultados.

## 10. Referências e Anexos

### Referências

- Falkenauer, E., & Delchambre, A. (1992). *A genetic algorithm for bin packing and line balancing.* Proceedings of the 1992 IEEE International Conference on Robotics and Automation, Nice, France, 1186-1192.
- Zakaria, Z., & Layeb, A. (2016). *Adaptive Cuckoo Search Algorithm for the Bin Packing Problem.* In Computational Intelligence and Optimization Methods for Control Engineering.

### Anexos

- **Dados Adicionais:**
  - Anexar tabelas ou gráficos adicionais, caso necessário.
- **Detalhes Técnicos:**
  - Fornecer informações complementares que possam ajudar na replicação dos experimentos.

## 11. Time

### Iago_123 não sabe falar fluxo em inglês

### Ricardo Vieira Chagas de Oliveira
<img src="https://avatars.githubusercontent.com/u/103327245?v=4" alt="ricaxov" width="50"/>

### Iago de Souza Lopes
<img src="https://avatars.githubusercontent.com/u/105664489?s=48&v=4" alt="iago_123" width="50"/>
