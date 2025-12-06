# 🏆 Análise Comparativa: Algoritmos Aproximativos para o Problema do Caixeiro Viajante

![Python](https://img.shields.io/badge/Language-Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Status-Finalizado-success?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

## 📋 Sobre o Projeto
Este projeto implementa e compara duas abordagens para o **Problema do Caixeiro Viajante (PCV)**:
- **Algoritmo Guloso (Vizinho Mais Próximo)** - Abordagem determinística e rápida
- **Meta-heurística (Otimização por Colônia de Formigas - ACO)** - Abordagem probabilística baseada em inteligência de enxame

**Equipe:** Davi Tuma Furtado, Elias Bariani Cardoso, Paulo Ricardo Silva Fonseca  
**Disciplina:** Análise e Projeto de Algoritmos  
**Data:** 05/12/2025

## 🎯 Objetivo
Avaliar o *trade-off* entre custo computacional e qualidade da solução para instâncias do PCV, demonstrando na prática conceitos teóricos de complexidade computacional.

## 🔬 Fundamentação Teórica

### Classes de Complexidade
- **Classe P:** Problemas resolvíveis em tempo polinomial
- **Classe NP:** Problemas cuja solução pode ser verificada em tempo polinomial
- **Classe NP-Difícil (NP-Hard):** Problemas tão difíceis quanto os mais difíceis de NP

### Classificação do PCV
O Problema do Caixeiro Viajante é **NP-Difícil**, com complexidade de força bruta **O(N!)**, tornando métodos exatos inviáveis para N > 20.

## ⚙️ Algoritmos Implementados

### 1. Algoritmo Guloso - Vizinho Mais Próximo (NN)
```python
def vizinho_mais_proximo(matriz_distancias, ponto_partida=0):
    # Implementação do algoritmo guloso
```

Complexidade: O(N²)
Estratégia: Seleciona sempre a cidade não visitada mais próxima
Vantagem: Extremamente rápido
Desvantagem: Visão "miope", tende a mínimos locais

### 2. Meta-heurística - Otimização por Colônia de Formigas (ACO)
python
class AntColonyOptimizer:
    # Implementação do ACO puro
Complexidade: O(I × K × N²)
Onde:

I = Número de iterações

K = Número de formigas

N = Número de cidades

Estratégia: Formigas artificiais constroem soluções baseadas em:

Feromônio (experiência coletiva)

Visibilidade (distância inversa)

Vantagem: Exploração global do espaço de busca
Desvantagem: Maior custo computacional

# 📊 Metodologia Experimental
Dados Utilizados
Cidades: 48 cidades do Rio Grande do Norte

Distâncias: Calculadas via Fórmula de Haversine

Fator de Tortuosidade: 1.29 (simulação de estradas reais)

Instâncias Testadas: 6, 12, 24, 36 e 48 cidades

Critérios de Avaliação
Tempo de execução (segundos)

Custo da rota (quilômetros)

# 📈 Resultados Obtidos
Tabela de Comparação
| N (Cidades) | Guloso (km) | Tempo (s) | ACO (km) | Tempo (s) | Melhoria ACO |
|:-----------:|:-----------:|:---------:|:--------:|:---------:|:------------:|
| **6** | 374.1       | 0.0000    | 344.6    | 0.1321    | 7.9%         |
| **12** | 947.2       | 0.0000    | 782.7    | 0.6089    | 17.4%        |
| **24** | 1483.9      | 0.0002    | 1328.8   | 6.3307    | 10.5%        |
| **36** | 1945.0      | 0.0003    | 1603.2   | 13.5906   | 17.6%        |
| **48** | 2046.4      | 0.0005    | 1950.7   | 24.5544   | 4.7%         |
# 📊 Análise dos Resultados
# 1. Qualidade da Solução (Distância)
ACO superou o Guloso em todas as instâncias

Melhorias variaram de 4.7% a 17.6%

Para 48 cidades: ACO encontrou rota 95.3 km mais curta

Explicação: O algoritmo guloso sofre de "miopia" - escolhas ótimas locais no início forçam saltos longos e custosos no final.

# 2. Desempenho Computacional (Tempo)
Guloso: Tempo desprezível (~0.0005s para 48 cidades)

ACO: Crescimento acentuado (~25s para 48 cidades)

Trade-off confirmado: Qualidade × Velocidade

## 🎯 Conclusões
# Principais Achados
Validação Teórica: Confirmação prática das classes de complexidade

Eficiência × Qualidade: Guloso é ordens de magnitude mais rápido, mas com soluções inferiores

Viabilidade do ACO: Tempo polinomial aceitável para qualidade superior

# Recomendações de Uso
Use Guloso quando: Tempo é crítico e soluções aproximadas são suficientes

Use ACO quando: Qualidade da solução é prioridade e há tempo disponível

## 🚀 Como Executar
# Requisitos
``` bash
pip install numpy matplotlib
```
# Execução
```bash
python arena_algoritmos.py
```
