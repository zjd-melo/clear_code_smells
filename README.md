## Clear code smells

[![linting: pylint](https://img.shields.io/badge/linting-pylint-yellowgreen)](https://github.com/pylint-dev/pylint)

>在每次提交之前进行 linter 检查。

## 说明
### 安装依赖
```shell
python -m venv venv --upgrade-deps
source venv/bin/active 
pip install -r requirements.txt
```

### 生成 pylint 配置文件 
`pylint --generate-toml-config > .pylintrc.toml`
### 生成 pre-commit 配置文件 
在项目根目录下创建 `.pre-commit-config.yaml` 文件，并配置如下 pylint hooks。
```yaml
repos:
  - repo: local
    hooks:
      - id: pylint
        name: pylint
        entry: pylint
        language: system
        types: [python]
        args:
          []
```
### 安装 git hooks
需要是个 git 仓库
`pre-commit install`

### 卸载 git hooks
`pre-commit uninstall`

### 其他
1. 默认情况下，只会对 git add 的文件进行 pylint，`pre-commit run --all-files` 可以对所有文件检查。

## 使用
- `git clone this repo` 
- `pip install -r requirements.txt`
- `pre-commit install`
