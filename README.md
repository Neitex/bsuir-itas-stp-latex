# Шаблон LaTeX для бугра этого вашего

_(no English readme, sorry)_

Подходит под требования СТП 2017 (скорее всего, под последний СТП потребуются минимальные изменения). Написанная с этим шаблоном курсовая была принята на 10 баллов в мае 2024.

Для сборки используется Docker и Makefile (при желании, без последнего можно обойтись, см. ниже). В README предполагается, что окружение - Linux с нужными правами для Docker + доступен `make`.

## Использование с Makefile

```bash
make note.pdf
```

Эта команда соберёт новый артифакт курсовой работы и поместит его рядом с Makefile'ом (естественно, запускать нужно находясь в одной папке с Makefile).

Также есть возможность автоматической генерации сниппетов кода с помощью Makefile'а. Подробнее см. в самом Makefile.

## Использование без Makefile

Теоретически, должно заработать и на Windows с Docker'ом (не проверялось).
```powershell
docker run --rm --user="1000:1000" --net=none -v "$PWD/note:/tmp" -w=/tmp neitex\:latex latexmk -pdflatex='pdflatex -shell-escape -interaction=nonstopmode -synctex=1 %O %S;' -pdf note.tex
```

## Лицензия

В соответствии с лицензиями софта, используемого здесь.

## Благодарность

Является своеобразным форком этого [репозитория](https://github.com/egorshulga/new-bsuir-diploma-latex). 
