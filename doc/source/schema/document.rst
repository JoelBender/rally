.. Document Repository Schema

Repository
==========

A **User** is an authenticated person, with a special user named *Guest User*
that represents someone or something that is accessing the site that has not
authenticated.

Repository Object
-----------------

.. class:: Repository

    A repository, a collection of documents.

.. attribute:: Repository._id

    The internal identifier of the repository object.

Create Repository
~~~~~~~~~~~~~~~~~

.. function:: create_repository(a, b, c)

    :param id group_id: group identifier
    :param id parent_id: wiki identifier or None

    Create a user.

Delete Repository
~~~~~~~~~~~~~~~~~

.. function:: delete_repository(repository_id)

    :param id user_id: user identifier

    Delete a user.

Modify Repository
~~~~~~~~~~~~~~~~~

.. function:: modify_repository(repository_id, **kwargs)

    :param id user_id: user identifier
    :param kwargs: attribute values

    Modify a user.

Document Object
---------------

.. class:: Document

    A repository, a collection of documents.

.. attribute:: Document._id

    The internal identifier of the repository object.

Create Document
~~~~~~~~~~~~~~~

.. function:: create_file(a, b, c)

    :param id group_id: group identifier
    :param id parent_id: wiki identifier or None

    Create a user.

Delete Document
~~~~~~~~~~~~~~~

.. function:: delete_file(document_id)

    :param id document_id: user identifier

    Delete a user.

Modify Document
~~~~~~~~~~~~~~~

.. function:: modify_file(document_id, **kwargs)

    :param id document_id: user identifier
    :param kwargs: attribute values

    Modify a user.

Folder Object
-------------

.. class:: Folder

    A repository, a collection of documents.

.. attribute:: Folder._id

    The internal identifier of the repository object.

Create Folder
~~~~~~~~~~~~~

.. function:: create_file(a, b, c)

    :param id group_id: group identifier
    :param id parent_id: wiki identifier or None

    Create a user.

Delete Folder
~~~~~~~~~~~~~

.. function:: delete_file(folder_id)

    :param id folder_id: user identifier

    Delete a user.

Modify Folder
~~~~~~~~~~~~~

.. function:: modify_file(folder_id, **kwargs)

    :param id folder_id: user identifier
    :param kwargs: attribute values

    Modify a user.

