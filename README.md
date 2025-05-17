1. ```mkdir drupal && cd drupal```
2. ```git clone repository with drupal web part```
3. copy files  from current repository for deployment into folder `drupal`
4. ```docker compose build```
5. ```docker compose up -d```
6. ```docker compose exec -it drupal_php /bin/bash``` then ```cd ..``` then ```composer install``` 
3. ```docker compose exec -i  drupal_db mysql -u username -p"paswword" name_of_database < backup.mysql```
4. copy folder `files` ---> `web/site/defalt/`
5. copy `setting.php`  ---> `web/site/defalt/`

