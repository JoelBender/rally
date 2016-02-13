.. Rally Documentation Master File

Rally
=====

This web site forum software is a mashup of the core features from a variety of
social web sites coupled with document sharing and task management tools.

* **public** content for users and guests

  * a *news section* for front page news, like a blog
  * a *reference section* for free-form content, a wiki
  * a *document repository* for white papers

* **protected** content for registered general interest users

  * a *question and answer* section, a simplified version of
    `OSQA <http://www.osqa.net/>`_ or
    `StackOverflow <http://stackoverflow.com/>`_

* **private** content for groups and their members

  * each group gets its own private *forum*, *document repository*, *wiki*,
    and *task board*
  * the forum and document repository together function like
    `Yahoo Groups <https://groups.yahoo.com/>`_
  * the task board is a
    `Kanban Board <https://en.wikipedia.org/wiki/Kanban_board>`_ that acts like
    `Trello <https://trello.com/>`_

Installation
------------

Clone the project on `GitHub <https://github.com/JoelBender/rally>`_::

    $ git clone https://github.com/JoelBender/rally

Go into the project folder and install::

    $ cd rally/
    $ ./install.sh

Follow the prompts during installation and your good to go!

Support
-------

To get help create an `issue <https://github.com/JoelBender/rally/issues>`_,
and `pull requests <https://github.com/JoelBender/rally/pulls>`_ are welcome.

Schema
------

While this project is getting off the ground, it would be good to review the
object and property definitions, beginning with the foundation classes.

.. toctree::
   :maxdepth: 2

   schema/index.rst

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
