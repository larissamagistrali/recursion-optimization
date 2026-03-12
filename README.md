# Otimização de Recursão

Este projeto demonstra diferentes abordagens para resolver um problema de contagem de senhas, comparando a performance entre recursão simples, recursão com memoização e solução iterativa.

## 📋 Descrição

O projeto implementa três soluções para calcular o número de senhas válidas de tamanho N, considerando restrições específicas entre caracteres. As implementações demonstram como diferentes técnicas de otimização podem melhorar drasticamente a performance de algoritmos recursivos.

## 🎯 Problema

Calcular o número total de senhas válidas de comprimento N, onde:

- Existem 5 caracteres possíveis (A, B, C, D, E)
- Alguns caracteres possuem restrições de posicionamento adjacente
- O algoritmo agrupa os caracteres em conjuntos ABE e CD com regras específicas

## 🚀 Implementações

### 1. RecursaoSemMemorizacao.java

**Recursão Simples**

Implementação recursiva direta sem otimização. Esta abordagem recalcula os mesmos valores múltiplas vezes, resultando em complexidade exponencial.

**Características:**

- ❌ Muito lenta para valores grandes de N
- ❌ Complexidade: O(2^n)
- ✅ Código simples e intuitivo

### 2. RecursaoComMemorizacao.java

**Recursão com Memoização (Top-Down)**

Utiliza programação dinâmica com abordagem top-down. Armazena resultados já calculados em arrays para evitar recomputação.

**Características:**

- ✅ Muito mais rápida que a recursão simples
- ✅ Complexidade: O(n)
- ✅ Usa menos memória que múltiplas chamadas recursivas
- ⚡ Cálculos são feitos apenas uma vez por subproblema

### 3. SemRecursao.java

**Solução Iterativa (Bottom-Up)**

Implementação iterativa usando programação dinâmica bottom-up. Constrói a solução de forma incremental sem chamadas recursivas.

**Características:**

- ✅ Mais eficiente em termos de espaço na pilha
- ✅ Complexidade: O(n)
- ✅ Sem overhead de chamadas recursivas
- ⚡ Melhor performance para valores muito grandes

## 💻 Como Executar

### Requisitos

- Java JDK 8 ou superior

### Compilação

```bash
# Compilar todas as classes
javac RecursaoSemMemorizacao.java
javac RecursaoComMemorizacao.java
javac SemRecursao.java
```

### Execução

Cada programa recebe como argumento o tamanho N da senha:

```bash
# Recursão sem memoização (use apenas para N pequenos, ex: N ≤ 20)
java RecursaoSemMemorizacao 10

# Recursão com memoização (eficiente para N ≤ 29 com long)
java RecursaoComMemorizacao 25

# Solução iterativa (mais eficiente para valores grandes)
java SemRecursao 29
```

**⚠️ Nota:** O tamanho máximo suportado com o tipo `long` é 29. Para valores maiores, seria necessário usar `BigInteger`.

## 📊 Comparação de Performance

| Abordagem             | Tempo para N=20         | Tempo para N=29    | Espaço     |
| --------------------- | ----------------------- | ------------------ | ---------- |
| Recursão Simples      | Muito lento (~segundos) | Inviável           | O(n) pilha |
| Recursão + Memoização | Rápido (~ms)            | Rápido (~ms)       | O(n)       |
| Iterativa             | Muito rápido (~ms)      | Muito rápido (~ms) | O(n)       |

## 🎓 Conceitos Demonstrados

- **Recursão:** Técnica onde uma função chama a si mesma
- **Memoização:** Técnica de otimização que armazena resultados de funções custosas
- **Programação Dinâmica:** Método para resolver problemas complexos dividindo-os em subproblemas mais simples
- **Top-Down vs Bottom-Up:** Duas abordagens diferentes para programação dinâmica
- **Análise de Complexidade:** Comparação entre O(2^n) e O(n)

## 📈 Exemplo de Saída

```bash
$ java SemRecursao 5
125

$ java RecursaoComMemorizacao 10
410338673

$ java SemRecursao 15
1903757311809
```

## 🔍 Análise Técnica

### Por que a recursão simples é lenta?

A recursão sem memoização recalcula os mesmos valores repetidamente. Para N=10, pode haver milhares de chamadas recursivas para calcular o mesmo valor.

### Como a memoização ajuda?

Ao armazenar resultados em arrays (`v1` e `v2`), cada subproblema é resolvido apenas uma vez, reduzindo drasticamente o número de operações.

### Vantagem da solução iterativa?

Elimina o overhead de chamadas de função e usa a pilha de forma mais eficiente, sendo ideal para valores grandes de N.
