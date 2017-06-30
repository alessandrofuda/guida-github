
# Mini guida github
#### Appunti per utilizzo minimale di github per il version control e deploy manuale  (testata con Laravel)


---



### 1) First configurations

---

(Attention! to Laravel owner/groups/permissions files and folders -- owners & groups should NOT be root !  --  permissions folders: 755 -- permissions files: 644  -- except `/storage` and `bootstrap/cache` --> `sudo chmod -R ug+rwx storage bootstrap/cache`)

---


##### a) On GITHUB

Create new repository on github --> through web interface --> "repositories" tab --> "New"



---


##### b) On DEV SERVER (localhost)

- `cd /../../myapp`

- `git init`

- `git config --global user.email "la-propria-email"`  #può essere anche quella di un altro account github

- `git config --global user.name "nome-utente"` #nome identicativo

- `git config --global push.default simple`

- `git remote add origin https://github.com/.....` (verify with `git remote -v`)



---


##### c) On PROD SERVER (remote)

-  connect via SSH

- `cd /../../myapp`

- `git init`

- `git config --global user.email "la-propria-email"`  #può essere anche quella di un altro account github

- `git config --global user.name "nome-utente"` #nome identicativo

- `git config --global push.default simple`

- `git remote add origin https://github.com/.....` (verify with `git remote -v`)



---



### 2) Daily Workflow

##### On Localhost

- `cd /home/~/.../myapp`

- `git pull`

- ... Edit Code ... :) :) :)

- `git status`  (to verify status)

- Upload new version to remote repository:

    - `git add .`   (-A || . || *)
    - `git commit -m "Messagio di riferimento"`
    - `git push` (--> username + password github account)



----------------------------------------------



### 3) Manual Deploy to PRODUCTION Server (!)


- Connect via SSH

- `sudo su -` (--> root privileges) (+ optional: `su - < my-current-username >` not root privileges)

- `git pull origin master`

- Check for overwritten data

- Clear all Laravel caches (routes/config/views..) (visit `php artisan list` )


---------------------------------------------


guida completa ITA: https://git-scm.com/book/it/v1/Per-Iniziare 

