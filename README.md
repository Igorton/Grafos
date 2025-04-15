# 📘 Projeto de Grafo em C#

Este projeto é uma implementação de uma estrutura de dados para **grafos**, desenvolvido como parte das atividades da disciplina de **Programação em C#**. Ele permite a criação, manipulação e análise de grafos com múltiplas funcionalidades.

---

## 👨‍🏫 Projeto acadêmico

Desenvolvido para fins de avaliação pelos alunos:

- **Igor Felipe Ton dos Santos** — RA: 113879  
- **Marcos Vinicius Nicolosi** — RA: 113624

---

## ⚙️ Funcionalidades

- Adicionar e remover vértices e arestas
- Renomear vértices
- Modificar pesos de arestas
- Verificar adjacência entre dois vértices
- Carregar grafo a partir de um arquivo `.txt`
- Executar o algoritmo de **Dijkstra** para encontrar o caminho mais curto

---

## 📁 Formato do Arquivo de Entrada

O arquivo deve conter uma lista de arestas. A **primeira linha é ignorada** (usada como cabeçalho, por exemplo). Cada linha válida deve ter três partes separadas por espaço:


---

## 🛠️ Melhorias e Correções

### ✅ 1. Remoção segura de vértices

- **Problema**: O método `RemoverVertice` podia lançar exceções por modificar a lista de arestas enquanto iterava por ela.
- **Solução**: A remoção agora é feita usando `RemoveAll` em uma lista separada, garantindo segurança durante a exclusão.

---

### ✅ 2. Validação da leitura de arquivos

- **Problema**: O código ignorava a primeira linha e assumia que o resto do arquivo estava formatado corretamente.
- **Solução**:
  - Verifica se o arquivo existe (`File.Exists`)
  - Verifica se cada linha tem exatamente 3 partes
  - Usa `double.TryParse` para validar o peso da aresta

---

### ✅ 3. Correção no algoritmo de Dijkstra

- **Problema**: Uso incorreto de `int.MaxValue` e `int` para distâncias, mesmo com pesos do tipo `double`.
- **Solução**: Substituído por `double.MaxValue` e ajustado todo o cálculo de distâncias para `double`, garantindo precisão e funcionamento correto.

---

### ✅ 4. Validação das entradas do usuário

- **Problema**: Entradas do console eram convertidas diretamente com `int.Parse()` e `double.Parse()` sem validação, podendo causar exceções.
- **Solução**:
  - Uso de `TryParse` para garantir que o valor digitado é válido antes de usar.
  - Mensagens de erro amigáveis informam ao usuário quando a entrada é inválida.

---

## ▶️ Como executar

1. Compile o projeto usando Visual Studio ou CLI (`dotnet build`)
2. Execute o projeto (`dotnet run` ou F5 no Visual Studio)
3. Siga o menu interativo no console para manipular o grafo

---

## ✅ Conclusão

Este projeto permitiu aplicar na prática os conceitos de:
- Estruturas de dados em grafos
- Leitura e análise de arquivos
- Algoritmos de caminhos mínimos (Dijkstra)
- Manipulação e tratamento de exceções em C#

Com as melhorias aplicadas, o sistema está mais robusto, seguro e pronto para lidar com diferentes arquivos e interações do usuário.

---

