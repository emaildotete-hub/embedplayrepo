# Extensão CloudStream - EmbedPlay

Esta é uma extensão para o aplicativo CloudStream Android que utiliza a API EmbedPlay para fornecer filmes e séries.

## Estrutura do Projeto

- `app/src/main/kotlin/com/example/EmbedPlayProvider.kt`: Lógica principal do provider (busca, carregamento, links).
- `app/src/main/kotlin/com/example/EmbedPlayPlugin.kt`: Classe de entrada do plugin.
- `build.gradle.kts`: Configurações de build do projeto.
- `app/build.gradle.kts`: Configurações de build do módulo da extensão.
- `repository.json`: Exemplo de como configurar seu repositório para o CloudStream.

## Como Compilar

Para gerar o arquivo `.cs3` (que é o formato de plugin do CloudStream), você deve usar o Gradle.

1. Certifique-se de ter o JDK 17+ instalado.
2. No terminal, na raiz do projeto, execute:
   ```bash
   ./gradlew make
   ```
3. O arquivo gerado estará em:
   `app/build/outputs/EmbedPlay.cs3`

## Como Adicionar no CloudStream

1. Hospede o arquivo `.cs3` e o `repository.json` em um servidor (ex: GitHub).
2. No CloudStream, vá em **Configurações** > **Extensões** > **Adicionar Repositório**.
3. Insira a URL do seu arquivo `repository.json`.
4. Instale a extensão "EmbedPlay" que aparecerá na lista.

## Requisitos Técnicos Implementados

- **Linguagem**: Kotlin
- **Coroutines**: Utilizadas para chamadas assíncronas.
- **API**: Integração com `https://embedplayapi.top/api`.
- **Funcionalidades**:
  - `search()`: Busca via AJAX da API.
  - `load()`: Carrega detalhes e episódios.
  - `loadLinks()`: Resolve links de streaming via endpoint de stream da API.
- **Padrão**: Segue a arquitetura oficial de providers do CloudStream 3.
