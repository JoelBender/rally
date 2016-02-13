.. TaskBoard Schema

TaskBoard
=========

TaskBoard classes.

TaskBoard Object
----------------

.. class:: TaskBoard

   A TaskBoard is a collection of column objects, which in turn contain tasks.
   A task is a member of a TaskBoard iff the task is a member of one of the
   columns of the TaskBoard.

.. attribute:: TaskBoard._id

   The internal identifier of the TaskBoard object.

.. attribute:: TaskBoard.group_id

   The identifier of the group that "owns" the wiki.  Access to the task board,
   its columns, and its tasks is governed by roles of the members of the group.

.. attribute:: TaskBoard.columns

   An array of Column objects.

.. function:: createTaskBoard()

   Create a TaskBoard.

   :return: a :class:`TaskBoard` object

.. function:: deleteTaskBoard(taskboard_id)

   :param id taskboard_id: task board identifier
   :return: None

   Delete a task board, all of its columns, and all of its tasks.  For every 
   task that is deleted, if the user initiating the transaction is not 
   the owner of the task, the task owner is notified of the deleted task.

Column Object
-------------

.. class:: Column

.. attribute:: Column._id

   The internal identifier of the object.

.. attribute:: Column.taskboard_id

   The internal identifier of the :class:`TaskBoard` to which this is a member.
   
.. attribute:: Column.tasks

   An array of Task objects.

.. attribute:: Column.title

   Inherited from :attr:`WikiPage.title`, the short description of the 
   column.

.. function:: createColumn(taskboard_id)

   :param id taskboard_id: task board identifier
   :return: a :class:`Column` object

   Create a column associated with a :class:`TaskBoard`.

.. function:: moveColumn(column_id, taskboard_pos)

   :param id column_id: column identifier
   :param int taskboard_pos: column position

   Move a column to a new position relative to other columns on its task 
   board.  Columns are not moved between boards.

.. function:: modifyColumn(column_id, column_title=value)

   :param id task_id: column identifier
   :param str column_title: attribute of the column
   :param value: new title of the column

   Modify a column.  The only attribute of the column that can be modified 
   with this transaction is the column name.

.. function:: deleteColumn(column_id)

   :param id column_id: column identifier

   Delete a column and all of its tasks.  For every 
   task that is deleted, if the user initiating the transaction is not 
   the owner of the task, the task owner is notified of the deleted task.

Task Object
-----------

.. class:: Task

   Something for someone to do.  Task inherits from :class:`WikiPage` for the
   description of the task and the wiki reference attributes.

.. attribute:: Task._id

   Internal identifier of the object.

.. attribute:: Task.taskboard_id

   The identifier of the :class:`TaskBoard` to which this task belongs.

.. attribute:: Task.column_id

   The identifier of the :class:`Column` to which this task belongs.

.. attribute:: Task.user_id

   The identifier of the :class:`User` to which this task is assigned, or
   None if the task is unassigned.  It is unlikely that the user assigned to 
   a task does not have a role in the group of the task board.  But in the 
   case where a user leaves a group, the users tasks are not reassigned, nor 
   do they become unassigned.

.. attribute:: Task.name

   Inherited from :attr:`WikiPage.name`, the name of the task, an
   automatically assigned identifier.

.. attribute:: Task.title

   Inherited from :attr:`WikiPage.title`, the short description of the 
   task.

.. attribute:: Task.text

   Inherited from :attr:`WikiPage.text`, the unformatted wiki text of the
   description of the task.

.. attribute:: Task.html

   Inherited from :attr:`WikiPage.html`, the wiki text rendered as HTML.

.. attribute:: Task.refs

   Inherited from :attr:`WikiPage.refs`, an array of object identifiers
   that the wiki description references.

.. function:: createTask(taskboard_id, column_id)

   :param id taskboard_id: task board identifier
   :param id column_id: column identifier
   :return: None

   Create a task.

.. function:: moveTask(task_id, column_id, column_pos)

   :param id task_id: task identifier
   :param id column_id: column identifier
   :param int column_pos: column position
   :return: None

   Move a task to a new position relative to other tasks in the same column 
   or in a different column.  If the user initiating the transaction is not 
   the owner of the task, the task owner is notified of the change.

.. function:: assignTask(task_id, user_id)

   :param id task_id: task identifier
   :param id user_id: user identifier or None
   :return: None

   Assign a task to a user.  If the user initiating the transaction is not 
   the current owner of the task, the current owner is notified of the change.
   If the user initiating the transaction is not the new owner of the task,
   the new owner is notified of the change.

.. function:: modifyTask(task_id, attr=value, ...)

   :param id task_id: task identifier
   :param str attr: attribute of the task
   :param value: new value of the attribute of the task
   :return: None

   Modify a task.  If the user initiating the transaction is not the owner of 
   the task, the task owner is notified of the change.

.. function:: deleteTask(task_id)

   :param id task_id: task identifier

   Delete a task.  If the user initiating the transaction is not the owner of 
   the task, the task owner is notified that the task has been deleted.
