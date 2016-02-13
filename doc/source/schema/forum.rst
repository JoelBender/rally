.. Forum Schema

Forum
=====

A **User** is an authenticated person, with a special user named *Guest User*
that represents someone or something that is accessing the site that has not
authenticated.

Forum Object
------------

.. class:: Forum

    A repository, a collection of documents.

.. attribute:: Forum._id

    The internal identifier of the repository object.

Create Forum
~~~~~~~~~~~~

.. function:: create_forum(a, b, c)

    :param id group_id: group identifier
    :param id parent_id: wiki identifier or None

    Create a user.

Delete Forum
~~~~~~~~~~~~

.. function:: delete_forum(forum_id)

    :param id forum_id: user identifier

    Delete a user.

Modify Forum
~~~~~~~~~~~~

.. function:: modify_forum(forum_id, **kwargs)

    :param id forum_id: user identifier
    :param kwargs: attribute values

    Modify a user

Article Object
--------------

.. class:: Article

    A repository, a collection of documents.

.. attribute:: Article._id

    The internal identifier of the repository object.

Create Article
~~~~~~~~~~~~~~

.. function:: create_file(a, b, c)

    :param id group_id: group identifier
    :param id parent_id: wiki identifier or None

    Create a user.

Delete Article
~~~~~~~~~~~~~~

.. function:: delete_topic(article_id)

    :param id article_id: user identifier

    Delete a user.

Modify Article
~~~~~~~~~~~~~~

.. function:: modify_topic(article_id, **kwargs)

    :param id article_id: user identifier
    :param kwargs: attribute values

    Modify a user

Comment Object
--------------

.. class:: Comment

    A repository, a collection of documents.

.. attribute:: Comment._id

    The internal identifier of the repository object.

Create Comment
~~~~~~~~~~~~~~

.. function:: create_comment(a, b, c)

    :param id group_id: group identifier
    :param id parent_id: wiki identifier or None

    Create a user.

Delete Comment
~~~~~~~~~~~~~~

.. function:: delete_comment(comment_id)

    :param id comment_id: user identifier

    Delete a user.

Modify Comment
~~~~~~~~~~~~~~

.. function:: modify_topic(comment_id, **kwargs)

    :param id comment_id: user identifier
    :param kwargs: attribute values

    Modify a user

Tag Object
----------

.. class:: Tag

    A repository, a collection of documents.

.. attribute:: Tag._id

    The internal identifier of the repository object.

Create Tag
~~~~~~~~~~

.. function:: create_comment(a, b, c)

    :param id group_id: group identifier
    :param id parent_id: wiki identifier or None

    Create a user.

Delete Tag
~~~~~~~~~~

.. function:: delete_comment(tag_id)

    :param id tag_id: user identifier

    Delete a user.

Modify Tag
~~~~~~~~~~

.. function:: modify_topic(tag_id, **kwargs)

    :param id tag_id: user identifier
    :param kwargs: attribute values

    Modify a user
