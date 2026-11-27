Aplicativo Flutter de catálogo de jogos gratuitos, desenvolvido com **Flutter** e **GetX** e integrado à API REST **FreeToGame**.

## Identificação

- **Aluno:** Denny Rondon
- **Turma:** ADS 2025
- **Disciplina:** Desenvolvimento de Sistemas Móveis

## Links

- **Repositório (código-fonte):** https://github.com/DennyRG/trabalho_flutter
- **Aplicação publicada (GitHub Pages):** https://dennyrg.github.io/trabalho_flutter/

## Funcionalidades

- Listagem de jogos com capas carregadas da internet (`GET /games`)
- Detalhes do jogo com nova requisição por ID (`GET /game?id=ID`)
- Filtro por plataforma (Windows, Navegador)
- Filtro por categoria (Shooter, MMORPG, Strategy, Racing)
- Ordenação (popularidade, ordem alfabética, lançamento)
- Atalhos de filtro em chips na tela principal
- Busca de jogos pelo nome (local, sem diferenciar maiúsculas e minúsculas)
- Jogos favoritos com `RxList` e `Obx`, sem duplicidade (comparação por ID)
- Tratamento de carregamento, erros, listas vazias e imagens indisponíveis
- Pull-to-refresh, carrossel de screenshots e layout responsivo
- Tema escuro em vermelho e preto

## Tecnologias

- Flutter
- GetX (`GetMaterialApp`, `GetConnect`, `GetxController`, `.obs`, `Obx`, `Get.to`, `Get.back`, `Get.snackbar`)
- url_launcher

## Estrutura do projeto

```
lib/
  main.dart
  theme/         app_theme.dart
  models/        game_model.dart, game_detail_model.dart
  services/      game_service.dart
  controllers/   game_controller.dart
  utils/         link_helper.dart
  components/    game_card.dart, state_views.dart, source_link.dart
  screens/       game_list_page.dart, game_detail_page.dart,
                 filter_page.dart, favorite_page.dart
```

## Como executar

1. Instale o [Flutter SDK](https://docs.flutter.dev/get-started/install)
2. Clone o repositório:
   ```
   git clone https://github.com/DennyRG/trabalho_flutter.git
   ```
3. Entre na pasta do projeto e instale as dependências:
   ```
   cd trabalho_flutter
   flutter pub get
   ```
4. Execute na versão Web:
   ```
   flutter run -d chrome
   ```

## Publicação no GitHub Pages

```
flutter build web --release --base-href "/trabalho_flutter/"
```

O conteúdo gerado em `build/web/` é publicado no GitHub Pages.

## API utilizada

Dados fornecidos por [FreeToGame.com](https://www.freetogame.com).

- URL base: `https://www.freetogame.com/api`
- Documentação: https://www.freetogame.com/api-doc

Apenas requisições `GET` são utilizadas. Não é necessário autenticação nem chave de API.
