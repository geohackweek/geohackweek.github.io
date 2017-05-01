## Steps to set current commit to the only initial commit (gets rid of all the SWC/NHW history in the commits)

git checkout --orphan latest_branch
git add -A
git commit -am "initial commit"
git branch -D gh-pages
git branch -m gh-pages
git push -f origin gh-pages
git gc --aggressive --prune=all
