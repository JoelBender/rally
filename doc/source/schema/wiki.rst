.. Wiki Schema

Wiki
====

A **Wiki** is a collection of wiki pages.

Wiki Classes
------------

.. class:: Wiki

This is a long line of text.

.. attribute:: Wiki._id

The internal identifier of the Wiki object, not exposed to the user.

.. class:: WikiPage

.. attribute:: WikiPage._id

The internal identifier of the Column object, not exposed to the user.

.. attribute:: WikiPage.name

The string name of the wiki page.

.. attribute:: WikiPage.text

The unformatted wiki text of the page.

.. attribute:: WikiPage.html

The wiki text rendered as HTML.

.. attribute:: WikiPage.refs

An array of object identifiers that this wiki page references.  They 
are commonly references to wiki pages within the same wiki, but may 
also be identifiers of documents, tasks, users, etc.

Wiki Transactions
-----------------

.. function:: createWiki()

   Create a Wiki.

   :return: the Wiki object with an identifier.

.. function:: deleteWiki(wid)

   Delete a Wiki and all of its pages.

   :param str wid: wiki identifier
   :return: none

