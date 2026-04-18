git init
git status
git add .
git config --global username ""
git config --global email ""
git remote add origin ""
git commit -m "Hello"
git push -u origin main master

git branch
git checkout -b "MITS"
git commit -m "changed"
git push
git push --set-upstream origin MITS
git pull

git log
git log --oneline

git clone "url"
cd "repository name"
git status

git add .
git commit -m "saved"
git branch -M main
git push -u origin main
