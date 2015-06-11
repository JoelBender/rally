.. Wiki Schema

Wiki
====

A **Wiki** is a collection of wiki pages.

Wiki Classes
------------

.. class:: Wiki

   A collection of :class:`WikiPage` instances.
   
.. attribute:: Wiki._id

   The internal identifier of the Wiki object.

.. attribute:: Wiki.parent_id

   The identifier of the parent wiki.  When wiki page references (names that
   match a :attr:`WikiPage.name`) are resolved to page identifiers (the
   :attr:`WikiPage._id` values) the search is within the current wiki, and 
   then if the wiki parent identifier is not *None*, process continues in the 
   context of the parent wiki.

.. attribute:: Wiki.group_id

   The identifier of the group that "owns" the wiki.  Access to the wiki pages
   is governed by roles of the members of the group.

.. class:: WikiPage

   A single page in a :class:`WIki`.

.. attribute:: WikiPage._id

   The internal identifier of the object.

.. attribute:: WikiPage.wiki_id

   The identifier of the wiki to which this page belongs.

.. attribute:: WikiPage.name

   The name of the wiki page, typically in upper camel case.

.. attribute:: WikiPage.title

   The title of the wiki page is typically the same as the name except for 
   those cases when the page name is not in upper camel case.  This attribute
   is an array of strings, each of which are are annotated with a language code.

.. attribute:: WikiPage.text

   The unformatted wiki text of the page.  This attribute is an array of
   strings, each of which are are annotated with a language code.

.. attribute:: WikiPage.html

   The wiki text rendered as HTML.  This attribute is an array of strings, each
   of which are are annotated with a language code.

.. attribute:: WikiPage.refs

   An array of object identifiers that this wiki page references.  They 
   are commonly references to wiki pages within the same wiki, but may 
   also be identifiers of documents, tasks, users, etc.

Wiki Transactions
-----------------

.. function:: createWiki(group_id, parent_id)

   :param id group_id: group identifier
   :param id parent_id: wiki identifier or None

   Create a Wiki.  The **parent_id** may be *None* if the wiki should not 
   inherit the names of the parent wiki pages.

   This transaction generates an additional :func:`createWikiPage` with a
   default name "FrontPage".

.. function:: deleteWiki(wiki_id)

   :param id wiki_id: wiki identifier

   Delete a Wiki and all of its pages.

Wiki Page Transactions
----------------------

.. function:: createWikiPage(wiki_id, name=value)

   :param id wiki_id: wiki identifier
   :param str name: the name of the wiki page

   Create a wiki page.

.. function:: modifyWikiPage(wikipage_id, attr=value, ...)

   :param id wikipage_id: task identifier
   :param str attr: attribute of the wiki page
   :param value: new value of the attribute of the wiki page

   Modify a wiki page.

.. function:: deleteWikiPage(wikipage_id)

   :param str wikipage_id: wiki page identifier

   Delete a wiki page.  Every wiki must have at least one page, so this 
   transaction will fail if this is the only page in the wiki.
