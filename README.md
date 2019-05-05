# MOCCA-prod

## What

Configuration files for the production deployment of MOCCA.

# Initial configuration

## Required system packages

To deploy this project you need to have a few dependencies installed ahead of
time as well as enabling a few repositories for some packages that are not in
the default repository.

First, add the repository for the required packages:

``` shell
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update
```

Then install the required packages:

``` shell
sudo apt install git nodejs yarn python3-venv python3-pip rabbitmq-server
```

Next, we also require `pipenv` for managing Python dependencies. However, due to
the ancient version of `pip` that comes with we also need to update it.

``` shell
sudo pip3 install -U pip
sudo pip3 install -U pipenv
```
