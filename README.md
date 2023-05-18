# TIMPlab04
```
mkdir TIMPlab04
переместила 5 файлов из 3 в 4 лабу
cd TIMPlab04
сделала первый комммит по инструкции с гита
mkdir .github
cd .github
mkdir workflows
cd workflows
touch CI.yml
nano CI.yml
```
```
name: CMake

on: # список триггеров для запуска процесса
 push:
  branches: [main]
 pull_request:
  branches: [main]

jobs: # список задач
 build_Linux: # наименование задачи

  runs-on: ubuntu-latest # система

  steps: # шаги задачи
  - uses: actions/checkout@v3

  - name: Configure Solver # наименование шага задачи
    run: cmake ${{github.workspace}}/solver_application/ -B ${{github.workspace}}/solver_application/build

  - name: Build Solver # наименование шага задачи
    run: cmake --build ${{github.workspace}}/solver_application/build

  - name: Configure HelloWorld # наименование шага задачи
    run: cmake ${{github.workspace}}/hello_world_application/ -B ${{github.workspace}}/hello_world_application/build

  - name: Build HelloWorld # наименование шага задачи
    run: cmake --build ${{github.workspace}}/hello_world_application/build
```

```
git add -A
git commit -m "commit"   
git push origin main

```
