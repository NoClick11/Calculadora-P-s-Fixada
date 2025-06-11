# Calculadora Pós-Fixada (Postfix Calculator)

Uma aplicação JavaFX que implementa uma calculadora para expressões em notação pós-fixada (Reverse Polish Notation - RPN), utilizando estruturas de dados fundamentais como pilha e fila.

## 📋 Índice

- [Sobre o Projeto](#sobre-o-projeto)
- [Funcionalidades](#funcionalidades)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Arquitetura](#arquitetura)
- [Pré-requisitos](#pré-requisitos)
- [Instalação e Execução](#instalação-e-execução)
- [Como Usar](#como-usar)
- [Exemplos de Uso](#exemplos-de-uso)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Algoritmo](#algoritmo)
- [Tratamento de Erros](#tratamento-de-erros)
- [Contribuição](#contribuição)
- [Licença](#licença)

## 🎯 Sobre o Projeto

A **Calculadora Pós-Fixada** é uma aplicação educacional desenvolvida em JavaFX que demonstra o uso prático de estruturas de dados (pilha e fila) para avaliar expressões matemáticas em notação pós-fixada. Este tipo de notação elimina a necessidade de parênteses e segue uma ordem de precedência natural, sendo amplamente utilizada em calculadoras HP e compiladores.

### O que é Notação Pós-Fixada?

Na notação pós-fixada (também conhecida como RPN - Reverse Polish Notation), os operadores são colocados após os operandos. Por exemplo:
- Infixa: `3 + 4` → Pós-fixada: `3 4 +`
- Infixa: `(3 + 4) * 2` → Pós-fixada: `3 4 + 2 *`

## ✨ Funcionalidades

- **Avaliação de expressões pós-fixadas** com operadores básicos
- **Interface gráfica intuitiva** desenvolvida em JavaFX
- **Tratamento robusto de erros** com mensagens descritivas
- **Suporte aos operadores**: `+`, `-`, `*`, `/`, `%`
- **Validação de entrada** para expressões malformadas
- **Feedback visual** dos resultados e erros
- **Limpeza automática** das estruturas de dados entre cálculos

## 🛠 Tecnologias Utilizadas

- **Java 8+** - Linguagem de programação
- **JavaFX** - Framework para interface gráfica
- **Estruturas de Dados Customizadas**:
  - Pilha (Stack) - para armazenar operandos
  - Fila (Queue) - para processar tokens sequencialmente

## 🏗 Arquitetura

O projeto segue uma arquitetura modular com separação clara de responsabilidades:

```
application.tratandoeventos/
├── MainApplication.java    # Classe principal e interface gráfica
├── Stack.java             # Implementação da estrutura de pilha
├── Queue.java             # Implementação da estrutura de fila
└── ViewController.java    # Controlador para FXML (não utilizado na versão atual)
```

### Padrões Utilizados

- **Separation of Concerns**: Cada classe tem uma responsabilidade específica
- **Custom Data Structures**: Implementação própria de pilha e fila usando LinkedList
- **Event-Driven Programming**: Interface responsiva baseada em eventos JavaFX

## 📋 Pré-requisitos

- **Java Development Kit (JDK) 8** ou superior
- **JavaFX SDK** (se não incluído no JDK)
- **IDE** recomendada: IntelliJ IDEA, Eclipse ou VS Code

### Verificação da Instalação

```bash
java -version
javac -version
```

## 🚀 Instalação e Execução

### 1. Clone ou Baixe o Projeto

```bash
git clone <url-do-repositorio>
cd calculadora-pos-fixada
```

### 2. Compilação

```bash
# Navegue até o diretório src
cd src

# Compile todas as classes
javac application/tratandoeventos/*.java
```

### 3. Execução

```bash
# Execute a aplicação principal
java application.tratandoeventos.MainApplication
```

### Execução via IDE

1. Importe o projeto na sua IDE preferida
2. Configure o JavaFX no classpath (se necessário)
3. Execute a classe `MainApplication.java`

## 📖 Como Usar

1. **Inicie a aplicação** - A interface gráfica será exibida
2. **Digite a expressão** no campo de texto usando notação pós-fixada
3. **Separe os elementos** com espaços (ex: `3 4 + 2 *`)
4. **Clique em "Calcular"** para processar a expressão
5. **Visualize o resultado** na área de texto inferior

### Regras de Entrada

- **Números**: Use números decimais (ex: `3.14`, `42`, `-5`)
- **Operadores**: `+`, `-`, `*`, `/`, `%`
- **Separação**: Use espaços entre todos os elementos
- **Formato**: Operandos primeiro, depois o operador

## 🎯 Exemplos de Uso

| Expressão Pós-fixada | Expressão Infixa Equivalente | Resultado |
|----------------------|------------------------------|-----------|
| `3 4 +` | `3 + 4` | `7.0` |
| `10 2 /` | `10 / 2` | `5.0` |
| `3 4 + 2 *` | `(3 + 4) * 2` | `14.0` |
| `15 7 1 1 + - *` | `15 * (7 - (1 + 1))` | `75.0` |
| `5 1 2 + 4 * + 3 -` | `5 + ((1 + 2) * 4) - 3` | `14.0` |
| `10 3 %` | `10 % 3` | `1.0` |

### Casos de Erro

| Entrada | Tipo de Erro | Mensagem |
|---------|--------------|----------|
| `3 +` | Operandos insuficientes | "Operandos insuficientes." |
| `3 4 5 +` | Expressão malformada | "Expressão malformada." |
| `3 0 /` | Divisão por zero | "Divisão por zero." |
| `3 # +` | Operador inválido | "Operador inválido: #" |

## 📁 Estrutura do Projeto

```
src/
└── application/
    └── tratandoeventos/
        ├── MainApplication.java    # 🖥️ Interface gráfica principal
        ├── Stack.java             # 📚 Estrutura de dados - Pilha
        ├── Queue.java             # 📋 Estrutura de dados - Fila
        └── ViewController.java    # 🎮 Controlador FXML (auxiliar)
```

### Descrição dos Componentes

#### MainApplication.java
- **Responsabilidade**: Interface gráfica e lógica principal
- **Componentes**: TextField, TextArea, Button
- **Funcionalidades**: Parsing, validação e cálculo das expressões

#### Stack.java
- **Estrutura**: Pilha (LIFO - Last In, First Out)
- **Implementação**: LinkedList<Double>
- **Operações**: push(), pop(), isEmpty(), size(), clear()

#### Queue.java
- **Estrutura**: Fila (FIFO - First In, First Out)
- **Implementação**: LinkedList<String>
- **Operações**: enqueue(), dequeue(), isEmpty(), clear()

## ⚙️ Algoritmo

O algoritmo de avaliação segue os seguintes passos:

### 1. Preparação
```java
1. Limpar pilha e fila
2. Dividir entrada em tokens (split por espaços)
3. Adicionar todos os tokens na fila
```

### 2. Processamento
```java
ENQUANTO fila não estiver vazia:
    token = retirar próximo da fila
    
    SE token é número:
        empilhar na pilha
    
    SENÃO SE token é operador:
        SE pilha tem menos de 2 elementos:
            ERRO: operandos insuficientes
        
        b = desempilhar
        a = desempilhar
        resultado = calcular(a, operador, b)
        empilhar resultado
    
    SENÃO:
        ERRO: token inválido
```

### 3. Finalização
```java
SE pilha tem exatamente 1 elemento:
    resultado = elemento da pilha
SENÃO:
    ERRO: expressão malformada
```

## 🛡️ Tratamento de Erros

A aplicação implementa tratamento robusto para diversos cenários de erro:

### Erros de Sintaxe
- **Operandos insuficientes**: Quando há menos de 2 números na pilha para um operador
- **Expressão malformada**: Quando sobram elementos na pilha após o processamento
- **Tokens inválidos**: Caracteres que não são números nem operadores válidos

### Erros Matemáticos
- **Divisão por zero**: Detectada nos operadores `/` e `%`
- **Números inválidos**: Tokens que não podem ser convertidos para Double

### Erros de Estado
- **Expressão vazia**: Entrada sem conteúdo
- **Estruturas não vazias**: Verificação de integridade pós-cálculo
