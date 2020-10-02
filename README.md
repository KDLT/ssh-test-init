# when creating a new repo

cd path/to/project/directory
# initialize the repository
git init
# add (to staging grounds) everything you changed kapag . ang gamit. pwede ring filenames
# apparently kaya . ibig sabihin ang pwd 'yan
git add .
# commit para secured na ang changes? staging ang tawag
git commit -m "commit  message"
# this just renames the current branch to main (master originally kapag kakagawa lang)
git branch -M main
# ssh ang gamit dito, once lang magaadd para makilala ng remote ang local
git remote add origin git@github.com:KDLT/ssh-test-init.git
# ganito magbato ng changes na magrereflect na sa git
git push -u origin main
