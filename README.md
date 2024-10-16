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

#### Simulated Annealing + Método de Bisecção
- **Parâmetros Utilizados:**
  - **Temperatura inicial**
  - **Taxa de resfriamento**
  - **Critério de parada**
  - **Método de bisecção**

- **Justificativa das Escolhas:**
  - A criação deste algoritmo(durante o desafio) partiu da curiosidade de testar uma ideia que surgiu. Ela consistiu em unir a lógica do SA(aceita soluções não apenas com base na sua qualidade mas também na temperatura atual) juntamente com o Método de Bisecção que divide o campo da solução em duas metades e decide se a solução está na esquerda ou na direita, repetindo o processo recursivamente.
  - A ideia do algoritmo foi feita da suscintamente da seguinte forma:
  -- *1* O Método de Bisecção serve para testar a melhor quantidade de caixas
  -- *2* Na função de try_packs(função para avaliar se a melhor solução está no bloco da direita ou da esquerda) para uma quantidade de caixas atual, é testado se a melhor configuração de itens está dentro ou não de um alcance de aceitação da quantidade atual de caixas atual dependendo da temperatura atual do sistema
    
  - O **Simulated Annealing** funciona com base no princípio do resfriamento gradual para escapar de mínimos locais. A escolha dos parâmetros foi guiada pela necessidade de **exploração** no início (temperatura alta), seguida de **intensificação** na busca (temperatura baixa). O uso da **bisecção** melhora a eficiência, ajustando o processo de busca. As taxas de cruzamento e mutação são menores, porque o foco do SA é ajustar pequenas variações de forma progressiva, ao contrário do GA, que depende de uma diversidade maior de soluções.

- Ponto positivo do algoritmo: Convergiu rapidamente para uma solução próxima da esperada(com um desvio máximo de 59 caixas no caso de teste com 5245 itens. Ou seja, a solução esperada = 2099, solução retornada = 2158)
- Ponto negativo do algoritmo: Com o código atual foi possível encontrar a quantidade aproximada de caixas, contudo não foi possível encontrar a configuração de itens de cada caixa

### Instâncias de Teste

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

### Gráficos
  - Instância com 500 itens

![WhatsApp Image 2024-10-15 at 17 25 24](https://github.com/user-attachments/assets/d3c50d5e-ec48-4fd3-9fa3-0022277408c8)

  - Instância com 1000 itens
    
![WhatsApp Image 2024-10-15 at 17 26 03](https://github.com/user-attachments/assets/7170d246-cb17-4700-aab3-e77b2b80b624)

  - Instância com 40 itens
    
![WhatsApp Image 2024-10-15 at 17 28 57](https://github.com/user-attachments/assets/9c39cebd-ce18-4c13-8acb-c8a76193bcf4)

  
## 5. Análise Comparativa

### Comparação com Outras Metaheurísticas

- **Algoritmos Comparados:**
  - Para conjuntos de dados maiores, é notável que tanto o Cuckoo Search quanto o Algoritmo Genético (GA) apresentaram desempenho inferior ao do Simulated Annealing (SA) com bisecção. No entanto, em conjuntos de dados menores, ambos os métodos se destacam em comparação ao SA com bisecção.
  
### Comparação com Soluções Ótimas ou Heurísticas

- **Soluções de Referência:**
  Utilizamos o Gurobi, um solver de programação matemática de alto desempenho, para obter soluções ótimas conhecidas para o problema de bin packing para pequenas instâncias e uso do benchmark do site unibe, principalmente dos arquivos do Falkenauer. Essas soluções serviram como referência para avaliar a eficácia dos algoritmos implementados.

- **Avaliação da Proximidade:**
  Analisamos a proximidade de cada algoritmo em relação à solução ótima obtida pelo Gurobi. Para essa avaliação, utilizamos o banco de dados BPPLIB, que contém instâncias de problemas de bin packing. A comparação nos permite identificar quão próximos os resultados dos algoritmos Cuckoo Search e Algoritmo Genético estão das soluções ótimas, além de fornecer uma perspectiva sobre a eficiência e a eficácia das abordagens heurísticas em relação às soluções exatas.

### Tempo de Execução
| N    |Tempo(SA+BS)| Tempo (GA) | Tempo (CS)  |
|------|------------|------------|-------------|
| 250  |            |            |  0.910s     |
| 500  |            |            |  3.200s     |
| 1000 |            |            | 65.000s     |
| 5245 | 12.700s    | 4140.20s   |     -       |

### Acurácia
| N    | Esperado | Acerto(SA+BS) | Acerto(GA) | Acerto(CS)  |
|------|----------|---------------|------------|-------------|
| 250  |          |               |            |             |
| 500  |          |               |            |             |
| 1000 |          |               |            |             |
| 5245 |          |               |            |             |



## 6. Discussão dos Resultados

### Interpretação

- **Significado dos Resultados:**
  Os resultados indicam que os desempenhos dos algoritmos utilizados foram satisfatórios em algumas instancias, contudo para instancias maiores nos algoritmos de GA e Cuckoo foi necessário diminuir o numero de gerações considerando os tempos de execução. 

- **Padrões Observados:**
  Identificamos padrões consistentes nas execuções, onde o desempenho dos algoritmos tende a melhorar à medida que o tamanho do problema diminui. Além disso, a variação nos resultados entre as diferentes execuções sugere que a aleatoriedade dos algoritmos pode influenciar os resultados, mas ainda assim, mantém uma qualidade satisfatória.

### Limitações

- **Qualidade das Soluções:**
  A qualidade das soluções geradas pode ser afetada pela escolha inadequada de hiperparâmetros e pela parametrização dos algoritmos. A seleção de parâmetros como taxa de mutação, número de gerações e tamanho da população teve um impacto significativo na eficiência e na eficácia dos algoritmos, indicando que uma otimização cuidadosa desses hiperparâmetros é essencial para melhorar os resultados.
  Outro aspecto limitação é o tempo curto para testes mais apronfundados principalmente pra verificar a capacidade do SA+BS 

## 7. Comparação com Objetivos Iniciais

### Alcançou os Objetivos?

- **Avaliação:**
  Após a realização dos experimentos, podemos afirmar que os objetivos propostos foram, em grande parte, atingidos. Os algoritmos implementados foram capazes de encontrar soluções competitivas para o problema de bin packing, e a comparação com soluções ótimas revelou a eficácia das abordagens adotadas.

- **Justificativas:**
  Os objetivos foram alcançados principalmente devido à implementação cuidadosa dos algoritmos e à utilização do Gurobi como referência para pequenas instâncias e ao benchmark do site unibe para testar soluções ótimas. No entanto, alguns objetivos poderiam ter sido melhor atingidos se tivéssemos realizado uma otimização mais rigorosa dos hiperparâmetros e explorado mais a hibridização entre os algoritmos.

### Surpresas ou Descobertas

- **Resultados Inesperados:**
  Um achado surpreendente foi a qualidade das soluções obtidas pelo Simulated Annealing (SA) com bisecção, que superou as expectativas iniciais. Esse desempenho destaca o potencial dessa abordagem em cenários específicos. Para aprimorar ainda mais os resultados, consideramos que uma melhor parametrização e a hibridização entre os algoritmos poderiam levar a melhorias significativas na qualidade das soluções encontradas.

## 8. Conclusão

### Síntese dos Achados

- **Resumo:**
  Os experimentos realizados com os algoritmos Cuckoo Search, Algoritmo Genético e Simulated Annealing (SA) com bisecção indicaram que, para instâncias menores, tanto o Cuckoo Search quanto o Algoritmo Genético apresentaram resultados satisfatórios, com tempos de execução competitivos. No entanto, para instâncias maiores, o SA com bisecção mostrou-se mais eficiente, gerando soluções mais próximas das ótimas conhecidas.

### Sugestões para Trabalhos Futuros

- **Otimização de Hiperparâmetros:**
  Um aspecto a ser explorado em trabalhos futuros é a otimização dos hiperparâmetros dos algoritmos implementados. A escolha dos parâmetros, como o tamanho da população, taxa de mutação e parâmetros de exploração no Cuckoo Search, mostrou ter um impacto significativo nos resultados. Métodos automáticos de ajuste, como busca em grade ou otimização bayesiana, poderiam ser investigados.

- **Hibridização de Algoritmos:**
  Outro caminho promissor é a hibridização entre algoritmos. A combinação das vantagens do Cuckoo Search, Algoritmo Genético e Simulated Annealing pode gerar abordagens mais robustas, que aproveitem as melhores características de cada técnica para melhorar a qualidade das soluções.

- **Escalabilidade e Paralelização:**
  Com o aumento da escala das instâncias do problema de bin packing, seria relevante investigar técnicas de paralelização para reduzir o tempo de execução dos algoritmos, especialmente para instâncias maiores.

- **Exploração de Outras Heurísticas:**
  Trabalhos futuros também poderiam explorar outras heurísticas e metaheurísticas, como Particle Swarm Optimization (PSO) ou Ant Colony Optimization (ACO), para comparar o desempenho com as abordagens implementadas.

- **Aplicações em Problemas Reais:**
  Por fim, a aplicação desses algoritmos em problemas reais de otimização relacionados a bin packing, como o planejamento logístico ou a alocação de recursos, poderia fornecer insights práticos adicionais e validar a eficácia das soluções encontradas em ambientes do mundo real.

## 9. Referências e Anexos

### Referências

- Falkenauer, E., & Delchambre, A. (1992). *A genetic algorithm for bin packing and line balancing.* Proceedings of the 1992 IEEE International Conference on Robotics and Automation, Nice, France, 1186-1192.
- Zakaria, Z., & Layeb, A. (2016). *Adaptive Cuckoo Search Algorithm for the Bin Packing Problem.* In Computational Intelligence and Optimization Methods for Control Engineering.

## 10. Time

### Iago_123 não sabe falar fluxo em inglês

### Ricardo Vieira Chagas de Oliveira
<img src="https://avatars.githubusercontent.com/u/103327245?v=4" alt="ricaxov" width="50"/>

### Iago de Souza Lopes
<img src="https://avatars.githubusercontent.com/u/105664489?s=48&v=4" alt="iago_123" width="50"/>
