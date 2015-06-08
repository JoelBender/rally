.. TaskBoard Schema

TaskBoard
=========

TaskBoard classes.

TaskBoard Classes
-----------------

.. class:: TaskBoard

A TaskBoard is a collection of column objects, which in turn contain tasks.  A task is a 
member of a TaskBoard iff the task is a member of one of the columns of the TaskBoard.

.. attribute:: TaskBoard._id

The internal identifier of the TaskBoard object, not exposed to the user.

.. attribute:: TaskBoard.columnList

An array of Column objects.

.. class:: Column

.. attribute:: Column._id

The internal identifier of the Column object, not exposed to the user.

.. attribute:: Column.name

The string name of the column.

.. attribute:: Column.taskList

An array of Task objects.

.. class:: Task

Something for someone to do.

TaskBoard Transactions
----------------------

.. function:: createTaskBoard()

   Create a TaskBoard.

   :return: the TaskBoard object

.. function:: deleteTaskBoard(tbid)

   Delete a TaskBoard, all of its Columns, and all of the tasks.

   :param str tbid: task board identifier
   :return: none

