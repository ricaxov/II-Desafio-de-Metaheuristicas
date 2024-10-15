# Análise de Resultados

## 1. Objetivos dos Experimentos

Os objetivos dos experimentos realizados são:

- Avaliar a eficiência dos algoritmos Genético (GA), Cuckoo Search, e uma variação do Simulated Annealing (SA) com método de bisecção.
- Testar diferentes parâmetros para cada um dos algoritmos e analisar seus impactos.
- Verificar a convergência da solução de cada algoritmo.
- Avaliar os trade-offs entre o tempo de execução e a qualidade da solução obtida.

## 2. Metodologia dos Experimentos

### Configurações dos Algoritmos

#### Cuckoo Search
- **Parâmetros Utilizados:**
  - Tamanho da população.
  - Taxas de cruzamento e mutação.
  - Número de gerações.
- **Justificativa das Escolhas:**
  - Explicar os critérios para a definição desses parâmetros com base em estudos anteriores ou experimentação preliminar.

#### Algoritmo Genético (GA)
- **Parâmetros Utilizados:**
  - Tamanho da população.
  - Taxas de cruzamento e mutação.
  - Número de gerações.
- **Justificativa das Escolhas:**
  - Fundamentar as escolhas com literatura ou experimentos iniciais que guiaram a definição dos parâmetros.

#### Simulated Annealing + Bisecção
- **Parâmetros Utilizados:**
  - Tamanho da população.
  - Taxas de cruzamento e mutação.
  - Número de gerações.
- **Justificativa das Escolhas:**
  - Explicar a relevância dos parâmetros escolhidos com base nas propriedades do problema e no comportamento do algoritmo.

### Instâncias de Teste

- **Descrição das Instâncias:**
  - Definir o tamanho dos problemas testados, complexidade, e características específicas.
- **Detalhes dos Dados:**
  - Indicar a origem dos dados e o processo de pré-processamento aplicado.

### Ambiente de Teste

- **Hardware:**
  - Informar especificações como CPU, memória RAM e demais características relevantes.
- **Software:**
  - Sistema operacional utilizado, linguagem de programação, e bibliotecas/dicionários de suporte empregados.

## 3. Apresentação dos Resultados

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

## 4. Análise Comparativa

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

## 5. Análise de Sensibilidade

### Influência dos Parâmetros

- **Variação de Parâmetros:**
  - Descrever as variações testadas nos parâmetros.
- **Impacto nos Resultados:**
  - Avaliar como as mudanças nos parâmetros afetaram o desempenho dos algoritmos.

### Robustez do Algoritmo

- **Consistência dos Resultados:**
  - Verificar se o algoritmo apresenta resultados estáveis em diferentes execuções.
- **Diversidade de Instâncias:**
  - Testar o algoritmo em diferentes tipos de problemas para avaliar sua adaptabilidade.

## 6. Convergência dos Algoritmos

### Curvas de Convergência

- **Gráficos de Evolução:**
  - Apresentar gráficos que mostram a evolução da aptidão ao longo das gerações.
- **Análise do Comportamento:**
  - Discutir o ritmo de convergência dos algoritmos.

### Exploração vs. Exploração

- **Balanceamento:**
  - Avaliar o equilíbrio entre exploração e exploração do espaço de busca.
- **Estratégias Utilizadas:**
  - Explicar as estratégias adotadas para manter esse equilíbrio.

## 7. Discussão dos Resultados

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

## 8. Comparação com Objetivos Iniciais

### Alcançou os Objetivos?

- **Avaliação:**
  - Avaliar se os objetivos dos experimentos foram atingidos.
- **Justificativas:**
  - Explicar por que os objetivos foram ou não alcançados.

### Surpresas ou Descobertas

- **Resultados Inesperados:**
  - Mencionar achados inesperados e possíveis insights decorrentes.

## 9. Sugestões para Trabalhos Futuros

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

## 10. Conclusão da Análise

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

## 11. Referências e Anexos

### Referências

- Falkenauer, E., & Delchambre, A. (1992). *A genetic algorithm for bin packing and line balancing.* Proceedings of the 1992 IEEE International Conference on Robotics and Automation, Nice, France, 1186-1192.
- Zakaria, Z., & Layeb, A. (2016). *Adaptive Cuckoo Search Algorithm for the Bin Packing Problem.* In Computational Intelligence and Optimization Methods for Control Engineering.

### Anexos

- **Dados Adicionais:**
  - Anexar tabelas ou gráficos adicionais, caso necessário.
- **Detalhes Técnicos:**
  - Fornecer informações complementares que possam ajudar na replicação dos experimentos.

---

# Descrição do Problema

O Problema de Empacotamento Unidimensional (1D Bin-Packing) é um clássico problema de otimização combinatória que se concentra em organizar um conjunto de itens em caixas de forma eficiente.

Nesse problema, são dados um conjunto de $N$ itens. Cada item $i$ possui um peso $W_i$, indicando que esse item consome $W_i$ unidades da capacidade de uma caixa. Também é dado um valor $C$, indicando a capacidade máxima de uma caixa.

O objetivo é empacotar todos os itens nas caixas de forma que o número total de caixas utilizadas seja o menor possível.

<p align="center">
  <img src="https://github.com/user-attachments/assets/1406f897-3bd5-4822-8e70-e228648f9900" alt="Conjunto de Itens" width="300"/>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/a59e4492-0385-4152-ad9a-d968d50022d8" alt="Solução Ótima" width="500"/>
</p>

---

## Time

### Ricardo Vieira Chagas de Oliveira
<p>
  <img src="https://avatars.githubusercontent.com/u/103327245?v=4" alt="ricaxov" width="50"/>
</p>

### Iago de Souza Lopes
<p>
  <img src="https://avatars.githubusercontent.com/u/105664489?s=48&v=4" alt="iago_123" width="50"/>
</p>
