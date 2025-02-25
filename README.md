## setup-ambiente-de-trabalho
Padronização da configuração do ambiente de desenvolvimento.

Um ambiente virtual isolado permite o gerênciamento de dependências de forma controlada, facilitando o versionamento de pacotes. Desta forma, o uso de pacotes instalados de forma global é desnecessária, tendo cada projeto um ambiente virtual isolado, evitando conflitos entre diferentes projetos.

Este repositório tem como sugestão, a configuração de um ambiente de trabalho (ambiente virtual + dependências) para desenvolvimento com python 3.X .
Esta configuração já foi testada e utilizada no Visual Studio Code, no desenvolvimento scripts para automatização no processamento e exportação de dados, desenvolvimento desktop com a utilização de Tkinter e desenvolvimento de APIs REST, com a utilização dos frameworks Django e Django REST Framework.

---

### Padronização dos commits
- `init`: commit inicial do projeto
- `lib`: adiciona nova biblioteca
- `feat`: (nova funcionalidade para o usuário)
- `fix`: (nova correção de bug para o usuário, nao correção de build script)
- `docs`: (mudança na documentação)
- `style`: (formatação, lint, falta de virgula, etc; não atualiza o codigo em produção)
- `refactor`: (refatoração de codigo em produção, ex. renomeação de variáveis)
- `test`: (adiciona testes, refatora tests; sem mudança em produção)
- `chore`: (atualização de tarefas, etapa de desenvolvimento; não atualiza código em produção)

---

### Dependências para execução de lint

Pre-commit: [https://pre-commit.com](https://pre-commit.com/), https://github.com/pre-commit/pre-commit

Flake8: https://flake8.pycqa.org/en/latest/index.html

Isort: https://pycqa.github.io/isort/

Black: https://pypi.org/project/black/

`pip install pre-commit flake8 isort black`

---

### Configuração arquivo .pre-commit-config.yaml

OBS: Atente-se para a versão do python que você está utilizando!!!

```
repos:
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v5.0.0
    hooks:
      - id: trailing-whitespace
      - id: check-json
      - id: end-of-file-fixer
      - id: name-tests-test
      - id: requirements-txt-fixer
  - repo: https://github.com/psf/black-pre-commit-mirror
    rev: 24.10.0
    hooks:
      - id: black
        language_version: python3.12.7
        stages: [pre-commit]
  - repo: local
    hooks:
      - id: requirements
        name: requirements
        entry: cmd /c 'pip freeze > requirements.txt; git add requirements.txt'
        language: system
        pass_filenames: false
        stages: [pre-commit]
  - repo: https://github.com/pycqa/isort
    rev: 5.13.2
    hooks:
      - id: isort
  - repo: https://github.com/pre-commit/mirrors-autopep8
    rev: "v2.0.4" 
    hooks:
      - id: autopep8
```

Executar os seguintes comando no prompt antes de inicializar o projeto:

```
pre-commit install
```
```
pre-commit autoupdate
```

### Configuração arquivos: .flake8 e pyproject.toml

Para configuração opicional das bibiotecas flake8 e black pode se criar arquivos .flake8 e pyproject.toml e customizar as configurações.
Porem, deve-se atentar para a criação de conflitos entre as configurações posteriores.

Exemplos:

```
# pyproject.toml
[tool.black]
line-length = 88
multi-line-output = 3
```

```
# .flake8

[flake8]
ignore = F401, E501
```

### Sugestão arquivo .gitignore para projetos python

https://github.com/github/gitignore/blob/main/Python.gitignore

### Sugestão arquivo .editorconfig para projetos python

https://github.com/ONSdigital/ons-python-template/blob/main/.editorconfig
