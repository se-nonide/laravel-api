# Laravel developer guide

This document defines the steps to follow to start development. How to install dependencies and other useful annotations

## Spftware requeriments
- PHP (Base language)
- Composer (Dependency manager)

## Installation of Composer

Run the following commands:
```
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
```

```
php -r "if (hash_file('sha384', 'composer-setup.php') === 'e21205b207c3ff031906575712edab6f13eb0b361f2085f1f1237b7126d785e826a450292b6cfd1d64d92e6563bbde02') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
```

```
sudo php composer-setup.php --install-dir=/bin --filename=composer
```

```
php -r "unlink('composer-setup.php');"
```

Or run the custom script provided `ìnstall_composer.sh`
