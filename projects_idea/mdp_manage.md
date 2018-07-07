# Mdp Manager

## Purpose

This project as the purpose of create a password manager who encrypt the data write on the disk and who link dinamikly login with passsword with website

## tech choice

* For a easy static linkage and for the defi I will develop this project with: GoLang language
* For the managing project I will try a tool that I never use: Pivotal Tracker
* For the versioning of the project I will use: Github

## what it should do and how it should do it

* It will work as a api rest who lesen on a file like docker for the version 1.0.
* The principal datafile will be encrypt with sha256 the encrypt key will be the uuid of the disk of where it's write.
* We will login with a hash of a login and a password as a key, it will gave us a token who will persist only as long as the server process will be up.
* In the encrypt file, every data execpt: the hash of the key and the list of all site; will be encrypt with a combinaison of the login and the clear pasword.
* The user will have:
  - a list of login
  - a list of password
  - and an assosiation list who associate login, password and site with there id.
