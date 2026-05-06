# Guia de Estudo: Jetpack Compose e Arquitetura Moderna no Android

## Contexto e Objetivos
Este repositório é o resultado de um estudo aprofundado sobre o Jetpack Compose, o kit de ferramentas moderno do Android para construção de interfaces nativas. O objetivo principal é compreender a transição do modelo imperativo (XML) para o paradigma declarativo, focando em como a interface reage a mudanças de estado de forma eficiente através da recomposição inteligente.
Objetivos de Estudo:

    Dominar os conceitos de Composição e Recomposição.
    Aplicar padrões de Gerenciamento de Estado (remember, mutableStateOf, State Hoisting).
    Explorar a integração do Compose com arquiteturas robustas como MVVM e MVI.

## Curadoria de Fontes
As seguintes fontes foram selecionadas e analisadas no NotebookLM para compor este material:

    Android Developers: "Como trabalhar com o Compose" - Guia fundamental sobre o paradigma declarativo.
    Android Developers: "Guia para a arquitetura do app" - Melhores práticas para apps escaláveis e testáveis.
    Philipp Lackner (YouTube): "How to Build an MVI Clean Code Weather App" - Aplicação prática de Clean Architecture com MVI.
    Philipp Lackner (YouTube): "MVVM vs. MVI" - Comparação técnica entre padrões de apresentação.
    GeeksforGeeks: "What is Clean Architecture in Android?" - Conceitos de separação de responsabilidades e camadas.

## Engenharia de Prompts e "Cicatrizes"
Durante a interação com a IA, foram exploradas diferentes abordagens para extrair informações técnicas precisas:

    Prompt Estratégico 1: "O que é o jetpack compose e qual seu objetivo?"
        Resultado: Definição clara como uma API declarativa que simplifica a manutenção da interface.
    Prompt de Variação (Refinamento): "Gere exemplos de bons usos do state e remember para que a composição e recomposição funcionem bem."
        Referência Obtida: Identificou-se a importância do rememberSaveable para sobreviver a mudanças de configuração.
    Troubleshooting (Dificuldades): Inicialmente, a IA forneceu resumos genéricos. Foi necessário solicitar especificamente "maus usos" para entender que operações pesadas (como ler SharedPreferences) dentro de um @Composable causam sérios problemas de desempenho.
## Miniguia de Estudo
### Resumo Estruturado: O Coração do Compose
O Jetpack Compose transforma dados em elementos de interface através de funções anotadas com @Composable. Ao contrário do sistema antigo, os widgets são relativamente sem estado e não expõem métodos como setText(). A atualização da tela ocorre via recomposição, onde o framework executa novamente apenas as funções cujos dados mudaram, ignorando o que permanece estático.
### Glossário de Conceitos Chave

    Composable: Função básica de UI; deve ser rápida, idempotente e livre de efeitos colaterais.
    Recomposição: Processo automático de redesenhar a UI quando o estado muda.
    State Hoisting (Elevação de Estado): Padrão de mover o estado para quem chama a função, tornando o componente "stateless" e facilitando testes.
    UDF (Unidirectional Data Flow): Padrão onde o estado desce e os eventos sobem, garantindo uma única fonte de verdade.
    MVI (Model-View-Intent): Arquitetura que trata o estado como uma unidade imutável, reagindo a "intenções" do usuário.

### Prompts Reutilizáveis para Revisão

    "Explique a diferença técnica entre CompositionLocal e State Hoisting."
    "Como o Jetpack Compose lida com a execução paralela de funções combináveis?".
    "Quais as vantagens de usar MVI em vez de MVVM em telas com estados complexos?".
