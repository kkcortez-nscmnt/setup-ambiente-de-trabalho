## setup-ambiente-de-trabalho
Padronização da configuração do ambiente de desenvolvimento.

Um ambiente virtual isolado permite o gerênciamento de dependências de forma controlada, facilitando o versionamento de pacotes, desta forma, o uso de pacotes instalados de forma global é desnecessária, tendo cada projeto um ambiente virtual isolado, evitando conflitos entre diferentes projetos.

Este repositório tem como sugestão, a configuração de um ambiente de trabalho (ambiente virtual + dependências) para desenvolvimento de APIs REST, com a utilização de Django REST Framework.

### Padronização dos commits
- `feat`: (nova funcionalidade para o usuário)
- `fix`: (nova correção de bug para o usuário, nao correção de build script)
- `docs`: (mudança na documentação)
- `style`: (formatação, lint, falta de virgula, etc; não atualiza o codigo em produção)
- `refactor`: (refatoração de codigo em produção, ex. renomeação de variáveis)
- `test`: (adiciona testes, refatora tests; sem mudança em produção)
- `chore`: (atualização de tarefas, etapa de desenvolvimento; não atualiza código em produção)

### Dependências para execução de lint

Pre-commit: [https://pre-commit.com](https://pre-commit.com/), https://github.com/pre-commit/pre-commit

Flake8: https://flake8.pycqa.org/en/latest/index.html

Isort: https://pycqa.github.io/isort/

Black: https://pypi.org/project/black/

`pip install pre-commit flake8 isort black`

### Configuração arquivo .pre-commit-config.yaml

OBS: Atente-se para a versão do python que está utilizando!!!

```
`repos:
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v3.3.0
    hooks:
      - id: trailing-whitespace
      - id: check-json
      - id: end-of-file-fixer
      - id: name-tests-test
      - id: requirements-txt-fixer
  - repo: https://github.com/psf/black-pre-commit-mirror
    rev: 23.7.0
    hooks:
      - id: black
        language_version: python3.11.5
        stages: [commit]
  - repo: https://github.com/pycqa/flake8
    rev: 6.1.0
    hooks:
      - id: flake8
        additional_dependencies:
          - flake8-bugbear
          - flake8-comprehensions
          - flake8-simplify
        stages: [commit]
  - repo: local
    hooks:
      - id: requirements
        name: requirements
        entry: cmd /c 'pip freeze > requirements.txt; git add requirements.txt'
        language: system
        pass_filenames: false
        stages: [commit]
  - repo: https://github.com/pycqa/isort
     rev: 5.12.0
     hooks:
       - id: isort
  - repo: https://github.com/pre-commit/mirrors-autopep8
    rev: "" # Use the sha / tag you want to point at
    hooks:
      - id: autopep8`
```

Executar os seguintes comando no prompt antes de inicializar o projeto:

```
pre-commit install
```
```
pre-commit autoupdate
```
