.. User Schema

User
====

A **User** is an authenticated person, with a special user named *Guest User*
that represents someone or something that is accessing the site that has not
authenticated.

User Object
-----------

.. class:: User

    A user.
   
.. attribute:: User._id

    The internal identifier of the user object.

Create User
~~~~~~~~~~~

.. function:: create_user(a, b, c)

    :param id group_id: group identifier
    :param id parent_id: wiki identifier or None

    Create a user.

Delete User
~~~~~~~~~~~

.. function:: delete_user(user_id)

    :param id user_id: user identifier

    Delete a user.

Modify User
~~~~~~~~~~~

.. function:: modify_user(user_id, **kwargs)

    :param id user_id: user identifier
    :param kwargs: attribute values

    Modify a user

Group Object
------------

.. class:: Group

    A group.
   
.. attribute:: Group._id

    The internal identifier of the user object.

Create Group
~~~~~~~~~~~~

.. function:: create_group(a, b, c)

    :param id group_id: group identifier
    :param id parent_id: wiki identifier or None

    Create a user.

Delete Group
~~~~~~~~~~~~

.. function:: delete_group(group_id)

    :param id group_id: user identifier

    Delete a user.

Modify Group
~~~~~~~~~~~~

.. function:: modify_group(group_id, **kwargs)

    :param id group_id: user identifier
    :param kwargs: attribute values

    Modify a user

