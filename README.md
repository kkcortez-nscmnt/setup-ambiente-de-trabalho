# setup-ambiente-de-trabalho
Padronização da configuração do ambiente de desenvolvimento.

Um ambiente virtual isolado permite o gerênciamento de dependências de forma controlada, facilitando o versionamento de pacotes, desta forma, o uso de pacotes instalados de forma global é desnecessária, tendo cada projeto um ambiente virtual isolado, evitando conflitos entre diferentes projetos.

Este repositório tem como sugestão, a configuração de um ambiente de trabalho (ambiente virtual + dependências) para desenvolvimento de APIs REST, com a utilização de Django REST Framework.

## Padronização dos commites
- `feat`: (new feature for the user, not a new feature for build script)
- `fix`: (bug fix for the user, not a fix to a build script)
- `docs`: (changes to the documentation)
- `style`: (formatting, missing semi colons, etc; no production code change)
- `refactor`: (refactoring production code, eg. renaming a variable)
- `test`: (adding missing tests, refactoring tests; no production code change)
- `chore`: (updating grunt tasks etc; no production code change)
