# A Self Tutorial For SSH and Github

## SSH Part
1. `ls -al ~/.ssh` to check for existing ssh keys
2. `ssh-keygen-t rsa -b 4096 -C "aguirrekenneth@gmail.com" -f ~/.ssh/id_rsa-kdlt` ang ginamit ko para may sariling bagong key itong KDLT account
3. `eval "$(ssh-agent -s)"; ssh-add ~/.ssh/id_rsa-kdlt` dito ako nagtagal kasi hindi ako nagbabasa, kung wala 'to hindi alam ni OPENSSH kung alin gagamitin na key
4. go to github profile -> click the dropdown triangle next to user photo -> Settings -> SSH and GPG keys -> New SSH Key; enter desired Title, in this case I used ArchKBA then proceed to next step
5. `xclip -sel clip < ~/.ssh/id_rsa-kdlt.pub` tapos i-paste ito sa lumZZabas sa public key text box sa item 4
6. `ssh -vT git@github.com` to test connection, note na ito ang exact commend para mag-test ng connection, kapag ayaw icheck ang verbose output, baka hindi na-add ang ssh key na na-generate kasi 'yan nangyari on my first try

## Git Part using the registered SSH Key

1. `cd path/to/project/directory` initialize the repository
git init

2. `git add .` add (to staging grounds) everything you changed kapag . ang gamit. pwede ring filenames. apparently kaya . ibig sabihin ang pwd 'yan
3. `git commit -m "commit  message"` commit para secured na ang changes? staging ang tawag
4. `git branch -M main` this just renames the current branch to main (master originally kapag kakagawa lang)
5. `git remote add origin git@github.com:KDLT/ssh-test-init.git` ssh ang gamit dito, once lang magaadd para makilala ng remote ang local
6. `git push -u origin main` ganito magbato ng changes na magrereflect na sa git

## Misc

- Napansin kong git trading ang nagcocommit, 'yun pala ang default user since nauna ko 'yun register-an ng public key, to update the commiter I used `git config --global user.name KDLT; git config --global user.email aguirrekenneth@gmail.com`
