# Rally

This web site forum software is a mashup of the core features from a variety of social web sites coupled with document sharing and task management tools.

## Content Categories

* *public* content for users and guests
  * a _news section_ for front page news, like a blog
  * a _reference section_ for free-form content, a wiki
  * _document repository_ for white papers
* *protected* content for registered general interest users
  * a _question and answer_ section, a simplified version of [OSQA](http://www.osqa.net/) or [StackOverflow](http://stackoverflow.com/)
* *private* content for groups and their members
  * each group gets its own private _forum_, _document repository_, _wiki_, and _task board_
  * the forum and document repository together function like [Yahoo Groups](https://groups.yahoo.com/)
  * the task board is a [Kanban Board](https://en.wikipedia.org/wiki/Kanban_board) that acts like [Trello](https://trello.com/)

## Foundation Schema

The core of the site is based on these foundation classes.

* a *User* is an authenticated person, with a special user named _guest_ that represents someone or something that is accessing the site that has not authenticated
* *Content* is an abstract class of a piece of web site content
* *Transaction* a description of an activity that creates, modifies, or deletes some content
  * transactions are not generated for _read_ activity
  * transactions have a _type identifier_ that describes the activity such as _postArticle_
  * each transaction has a timestamp and a reference to the user that initiated the activity

To help organize and manage content, there are these additional classes.

* *Group* is a collection of users
* *Role* is a set of transaction type identifiers that describe behaviors, rights, and obligations of a user with respect to the users participation in a group
* *Notifications* is a collection of short messages regarding site activity
  * new question or answer
  * files that are uploaded
  * tasks that are created
  * etc.

## Forum

Forums are used in three different ways in the site, but with very similar presentation.

In the _News Forum_ the articles are similar to a news site or blog, without a public comment section.
In the future there may be a way for comments to be made available to the members of the News Group, 
provided there is a trivially simple way to delete spam comments.

In the _Question and Answer Forum_ the articles are considered questions, and comments are considered 
proposed answers.  In the future there may be a way to mark an answer as "accepted".

In the _Group Forum_ where the content is only visible to members of the group, the content has no special 
designation.

* an *Article* is a message in a forum
* a *Comment* is a text message following up on an article
* a *Tag* is a label that is used to group similar articles together, commonly called a _hash tag_ from its appearance with an octothorp prefix

## Document Repository

A document repository is a collection of documents which are shared between members of a group.
There is a special _Guest Repository_ which contains documents that are available to the 
_Guest User_, which is the general public.

* a *Document* is an individual file such as Word, Excel, or PDF.  A document may be _current_ or _obsolete_, where obsolete documents have a reference to the next latest version and are excluded from the archive
* a *Folder* is a sub-collection of documents
* an *Archive* is a virtual zipped collection of current documents
  * the archive is a quick and easy way to download all of the current documents in the repository in a structure that matches the folder structure.

In the future there will be a way to map repository content to [ownCloud](https://owncloud.org/) to make it easier to mirror and access from desktop, Android, and iOS users.

## Wiki

Wiki text formatting is used for all text content on the site, including forum articles, comments, and task descriptions.  The current plan is to use [Creole](http://www.wikicreole.org/attach/CheatSheet/creole_cheat_sheet.png) or a close derivative.

* a *Wiki Page* is a page of wiki text.  It can refer to other wiki pages, documents in a repository, or general hyperlinks.

## Task Board

Every group gets a private task board with a collection of tasks.  Tasks are assigned to group members and arranged in columns.  Users have their own personal board which is the combined view of all of the tasks that have been assigned to them in their groups.

* a *Task Board* is a collection of columns.
* a *Column* is a collection of tasks that represent a task state such as _ToDo_, _Doing_, or _Done_.
  * each group cooperatively decides the number and titles of columns
* a *Task* is a description of some activity.





