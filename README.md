# guida-github
Appunti per utilizzo minimale di github per il deploy



Optional:
Create new repository --> through github web interface --> "repositories" tab --> "New" button



Only first configuration:
git config --global user.email "la-propria-email"  #può essere anche quella di un altro account github 
git config --global user.name "nome-utente" #nome vostro identicativo
git config --global push.default simple



Steps

0) Go into my app folder (localhost):
  - cd /home/~/.../myapp
 
1) Download repository:
  - git clone <url>

  If repo already downloaded --> only sync with pull
  - git pull



2) ... Edit Code ... :) :) :)



3) verify status --> 'git status'


4) upload new version to remote repository:

  - git add -A   (-A || . || *)
  - git commit -m "Messagio di riferimento"
  - git push (--> username + password github account)





