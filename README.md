
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

- install Laravel project

- `cd /../../myapp`

- `git init`

- `git config --global user.email "la-propria-email"`  #può essere anche quella di un altro account github

- `git config --global user.name "nome-utente"` #nome identicativo

- `git config --global push.default simple`

- `git remote add origin https://github.com/.....` (verify with `git remote -v`)



---


##### c) On PROD SERVER (remote)

- connect via SSH

- `sudo su -` (--> root)

- `su - <my-username>` (--> important)

- install Laravel project (set/verify RIGHT permissions --> see above)

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

- `git status` (for inspection)

- `git pull` (sync with github repo)

- ... Edit Code ... :) :) :)

- `git status`  (to verify status)

- Upload new version to remote repository:

    - `git add .`   (-A || . || *)
    - `git commit -m "Messaggio di riferimento"`
    - `git push` (--> username + password github account)



----------------------------------------------



### 3) Manual Deploy to PRODUCTION Server (!)

- ( Before: on Local machine: `composer install --optimize-autoloader` )


- Connect to Remote via SSH

- + optional: `su - < my-current-username >` --> NO root privileges!

- `php artisan down`

- `git pull origin master`

- `composer install --optimize-autoloader`

- `composer install` (load eventual new packages installed (from composer.lock)

- `composer update` (ignores the composer.lock file and downloads NEW libraries added in composer.json)

- `php artisan migrate --force --no-interaction` (create eventual new tables in db)

- `php artisan optimize`

(clear all caches)

- `php artisan config:clear`

- `php artisan route:clear`

- `php artisan view:clear`

- `php artisan cache:clear`

(If need Optimization: re-create caches)

- `php artisan config:cache`

- `php artisan route:cache` 

(Imp!)

- `php artisan up`

- Check for overwritten ONLINE data


    
    
    
    


---------------------------------------------


guida completa ITA: https://git-scm.com/book/it/v1/Per-Iniziare 

***

