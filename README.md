echo "Репозиторий с ветками и тэгами" > README.md
git add README.md
git commit -m "Добавил README.md"
git tag -a "V0" -m "Версия 0"
git push --follow-tags

git checkout -b feature
touch feature1.txt
git add feature1.txt
git commit -m "Добавил фичу feature1.txt"
git push -u origin feature

git checkout main
git merge feature -m "Слияние ветки feature в main"
git tag -a "V0.1" -m "Версия 0.1"
git push --follow-tags

git checkout feature
git checkout -b hotFix
touch hotFix1.txt
git add hotFix1.txt
git commit -m "Добавил фикс hotFix1.txt"
git push -u origin hotFix

git checkout main
git merge hotFix -m "Слияние ветки hotFix в main"
git tag -a "V0.1.1" -m "Версия 0.1.1"
git push --follow-tags
