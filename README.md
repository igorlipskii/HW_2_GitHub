1. На локальном репозитории сделать ветки для:
- Postman\
`git branch Postman`

- Jmeter\
`git branch Jmeter`

- CheckLists\
`git branch CheckLists`

- Bug Reports\
`git branch Bug_Reports`

- SQL\
`git branch SQL`

- Charles\
`git branch Charles`

- Mobile testing\
`git branch Mobile_testing`

2. Запушить все ветки на внешний репозиторий\
`git push origin --all` - все ветки сразу\
`git push -u origin nameBranch` - добавить одну ветку


2.1. Удаление ветки локально и на внешнем репозитории\
`git branch -d nameBranch` - локальное удаление\
`git push origin :nameBranch` - внешнее удаление

 
3. В ветке Bug Reports сделать текстовый документ со структурой баг репорта\
`git checkout Bug_Reports`\
`vim bug_report.txt`\
`I`

```txt
Project: Calculator
ID: 88
Summary: Результат умножения неверен
Description: Результат равен ожидаемому результату +2
    Steps to reproduce:
    Step 1: Открыть сайт https://nuix.github.io/SDET/senior-sdet/stagingCalc/index.html
    Step 2: Нажать цифру 6
    Step 3: Нажать знак умножения
    Step 4: Нажать цифру 3
    Step 5: Нажать знак равно
Actual result: 20
Expected result: 18
Attachments: https://somup.com/c3nq02TjpH
Severity: Critical
Priority: High
Labels: Smoke
Environment:
Operational system: macOS Big Sur 11.6.4
Browser version: Google Chrome 98.0.4758.102
Author: Igor Lipskii
Test Data: 27.02.2022
```

`ESC` `:` `wq`

4. Запушить структуру багрепорта на внешний репозиторий\
`git add bug_report.txt`\
`git commit -m "add bug report"`\
`git push --set-upstream origin Bug_Reports`

5. Вмержить ветку Bag Reports в Main\
`git checkout main`\
`git merge Bug_Reports`

6. Запушить main на внешний репозиторий.\
`git push`

7. В ветке CheckLists набросать структуру чек листа.\
`git checkout CheckLists`\
`vim checklist.txt`\
`I`

```txt
Project: Calculator
Bild: version_1

Name:
Проверить работу фунции умножения чисел.

Priority:
Higt

Component:
Умножение

Labels:
Smoke

Steps:
1. Открыть сайт https://nuix.github.io/SDET/senior-sdet/stagingCalc/index.html
2. Нажать на любую цифру
3. Нажать знак умножения
4. Нажать любую цифру
5. Нажать знак ровно

Test data:

Expected Result:
1. Сайт открывается
2. В окне результата отоброжается нажатая цифра
3. В окне результата отоброжается знак умножения
4. В окне результата отоброжается нажатая цифра
5. В окне результата отоброжается сумма умноженных цифр

Result:
```
`ESC` `:` `wq`

8. Запушить структуру на внешний репозиторий\
`git add checklist.txt`\
`git commit -m "add checklist structure"`\
`git push --set-upstream origin CheckLists`

9. На внешнем репозитории сделать Pull Request ветки CheckList в main\
`Заходим на GitHub в наш репозиторий HW_2_GitHub`\
Переходим в раздел `Pull Request`\
В разделе `Compare changes` выбираем из какой ветки и в какую хотим сделать Pull Request `base: main` `compare: CheckList`\
Нажимаем зеленую кнопку `Create pull request`\
Пишем commit `add checklist structure` и нажимаем ниже еще раз `Create pull request`\
Проверяем отсутствие конфликтов и нажимаем зеленую кнопку `Confirm merge`


10. Синхронизировать Внешнюю и Локальную ветки Main\
`git checkout main`\
`git pull`
