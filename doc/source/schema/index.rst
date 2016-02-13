.. Schema

Foundation Schema
=================

The core of the site is based on these foundation classes.

* a :class:`User` is an authenticated person, with a special user named
  *Guest User* that represents someone or something that is accessing the
  site that has not authenticated
* :class:`Content` is an abstract class of a piece of web site content
* :class:`Transaction` a description of an activity that creates, modifies, or
  deletes some content

  * transactions are not generated for read activity
  * transactions have a *function identifier* that describes the activity such
    as *postArticle*
  * each transaction has a timestamp and a reference to the user that initiated
    the activity, along with a reference to their session

To help organize and manage content, there are these additional classes.

* :class:`Group` is a collection of users
* :class:`Role` is a set of transaction type identifiers that describe
  behaviors, rights, and obligations of a user with respect to the users
  participation in a group
* :class:`Notifications` is a collection of short messages regarding site
  activity

  * new question or answer
  * files that are uploaded
  * tasks that are created
  * etc.

* :class:`Session` maintains session information such as the user, when the
  session was initiated, and other tracking information like the browser

Forum
-----

A :doc:`forum` is a collection of articles like a news site, or the first email
message in a thread for Yahoo Groups, or an initial share on Google+.  Forums
are used in three different ways in the site, but with very similar
presentation.

In the *News Forum* the articles are similar to a news site or blog, without a
public comment section. In the future there may be a way for comments to be
made available to the members of the News Group, provided there is a trivially
simple way to delete spam comments.

In the *Question and Answer Forum* the articles are considered questions, and
comments are considered proposed answers.  In the future there may be a way to
mark an answer as "accepted".

In the *Group Forum* where the content is only visible to members of the group,
the content has no special designation.

* a :class:`Forum` is a collection of articles
* an :class:`Article` is a message in a forum
* a :class:`Comment` is a text message following up on an article
* a :class:`Tag` is a label that is used to group similar articles together,
  commonly called a *hash tag* from its appearance with an octothorp prefix

Document Repository
-------------------

A :doc:`document` is a collection of documents which are shared between members
of a group. There is a special *Guest Repository* which contains documents that
are available to the *Guest User*, which is the general public.

* a :class:`Document` is an individual file such as Word, Excel, or PDF.  A
  document may be *current* or *obsolete*, where obsolete documents have a
  reference to the next latest version and are excluded from the archive
* a :class:`Folder` is a sub-collection of documents
* an :class:`Archive` is a virtual zipped collection of current documents

  * the archive is a quick and easy way to download all of the current documents
    in the repository in a structure that matches the folder structure.

In the future there will be a way to map repository content to
`ownCloud <https://owncloud.org/>`_ to make it easier to mirror and access from
desktop, Android, and iOS users.

Wiki
----

Every group gets a private :doc:`wiki` with a collection of wiki pages.  Wiki
text formatting is used for all text content on the site, including forum
articles, comments, and task descriptions.  The current plan is to use
`Creole <http://www.wikicreole.org/attach/CheatSheet/creole_cheat_sheet.png>`_
or a close derivative.

* a :class:`Wiki` is a collection of columns.
* a :class:`WikiPage` is a page of wiki text.  It can refer to other wiki
  pages, documents in a repository, or general hyperlinks.

Task Board
----------

Every group gets a private :doc:`taskboard` with a collection of tasks.  Tasks
are assigned to group members and arranged in columns.  Users have their own
personal board which is the combined view of all of the tasks that have been
assigned to them in their groups.

* a :class:`TaskBoard` is a collection of columns.
* a :class:`Column` is a collection of tasks that represent a task state such
  as *ToDo*, *Doing*, or *Done*.

  * each group cooperatively decides the number and titles of columns

* a :class:`Task` is a description of some activity.

Detailed Definitions
====================


.. toctree::

   user.rst
   forum.rst
   document.rst
   wiki.rst
   taskboard.rst
