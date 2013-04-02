Running Flower on Dotcloud
==========================

    `Flower <https://github.com/mher/flower>`_ is a web based tool for monitoring and administrating Celery clusters.

Augmenting your project to use Flower is easy:

1. Clone this repository to your project root::

    $ git clone https://github.com/johncosta/flower-on-dotcloud flower

2. Remove the hidden git repository::

    $ rm -rf flower/.git

3. Add flower to your dotcloud.yml file::

    flower:
        type: python-worker
    approot: flower
    ports:
        flower: http
    processes:
        flower: flower --port=$PORT_FLOWER --broker=$DOTCLOUD_DATA_REDIS_URL/0

.. note::  Your environment variables for your redis broker might be slightly different.  Also double check your database id.


