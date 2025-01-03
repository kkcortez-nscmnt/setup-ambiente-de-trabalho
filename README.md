# setup-ambiente-de-trabalho
Padronização da configuração do ambiente de desenvolvimento.

Um ambiente virtual isolado permite o gerênciamento de dependências de forma controlada, facilitando o versionamento de pacotes, desta forma, o uso de pacotes instalados de forma global é desnecessária, tendo cada projeto um ambiente virtual isolado, evitando conflitos entre diferentes projetos.

Este repositório tem como sugestão, a configuração de um ambiente de trabalho (ambiente virtual + dependências) para desenvolvimento de APIs REST, com a utilização de Django REST Framework.

## Padronização dos commits
- `feat`: (nova funcionalidade para o usuário)
- `fix`: (nova correção de bug para o usuário, nao correção de build script)
- `docs`: (mudança na documentação)
- `style`: (formatação, lint, falta de virgula, etc; não atualiza o codigo em produção)
- `refactor`: (refatoração de codigo em produção, ex. renomeação de variáveis)
- `test`: (adiciona testes, refatora tests; sem mudança em produção)
- `chore`: (atualização de tarefas, etapa de desenvolvimento; não atualiza código em produção)

## Dependências para execução de lint

Pre-commit: [https://pre-commit.com](https://pre-commit.com/), https://github.com/pre-commit/pre-commit

Flake8: https://flake8.pycqa.org/en/latest/index.html

Isort: https://pycqa.github.io/isort/

Black: https://pypi.org/project/black/

`pip install pre-commit flake8 isort black`
