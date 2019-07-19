# Media Library

## Purpose

Create an interactive database for media gestion

## Versionning

Name of game of thron character

## Git gestion

We will have many master branch:
 - `master` contain:
   - haproxy and database deploy script
   - build/push script
   - general deploy script in local
 - `front/master` contain:
   - source code
   - deploy script to test
 - `back_1/master` contain:
   - source code
   - deploy script to test
 - `back_2/master` contain:
   - source code
   - deploy script to test
 - `back_.../master` contain:
   - source code
   - deploy script to test
 - `doc/master` contain:
   - the global documentation
 - `ansible/master` contain:
   - the ansible to deploy and update version with no down time

every master will comme from a diff origin

every master will have be on gitflow model

every tag will be `{{ prefix }}-{{ version_name }}`

## Need

what we need for our app to be finish:
 - User managemer:
   - register
   - login
   - logout
 - User Platforme
   - Print content
     - List of categorie (manga, comics, film) that we have
     - Then when we click on a categorie it show the list off collection that we have add:
       - we can add a collection to our list of collections
       - we can see every collection and if we have finished it.
     - Then when we click on a collection it show the list off content we have in this collection
       - we can see the total of content availible in the world for this collection
       - we can see some data like author editor productor description
       - we can see if the collection is finished
       - we can see if we have completed this collection
       - we can tag if we want to finish this collection
   - Print Missing
     - print the list of the missing content according to the tag
     - change is-complete of Users-Collections in db 0 if not 1 if yes
   - Add Categorie
     - we need to be able to add content in our list of content
   - Add Collections
     - We need to be able to add content in our list of content
   - Add Contents
     - We need to be able to add content in our list of content
   - Propose Categorie/Collections/Content
     - We need to be able to propose Categories, Collections and Content for global list
 - Admin Platforme
   - User gestion
   - Proposition gestion (validation or not)
   - Add/Edit Categories
   - Add/Edit Collections
   - Add/Edit Content

 - Our app need one or more api-doc
 - Our app as to be dockerised
 - Our app as to be deployed with ansible
 - Our app need to have a backup process
 - Our app need to have a restore process (a ansible script would be great)


## Database

structure:
 - User
    - id
    - login
    - password
    - mail

 - Tokens
    - id
    - token
    - user_id

 - Users-Categories
    - id
    - user-id
    - categorie-id
 - Users-Collections
    - id
    - user-id
    - collection-id
    - is-complete
    - want-to-complete
 - Users-Contents
    - id
    - user-id
    - content-id

 - Categories
    - id
    - name
    - collection-row-1 (to what collection-row-1 correspond in Collections)
    - collection-row-2 (to what collection-row-2 correspond in Collections)
    - ...
 - Collections
    - id
    - name
    - total
    - collection-row-1
    - collection-row-2
    - ...
    - content-row-1 (to what content-row-1 correspond in Contents)
    - content-row-2 (to what content-row-2 correspond in Contents)
    - ...
 - Contents
    - id
    - number
    - content-row-1
    - content-row-2
    - ...
