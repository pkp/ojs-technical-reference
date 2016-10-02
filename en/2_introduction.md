# Introduction

The design of Open Journal Systems 2.x is heavily structured for maintainability, flexibility and robustness. For this reason it may seem complex when first approached. Those familiar with Sun's Enterprise Java Beans technology or the Model-View-Controller (MVC) pattern will note many similarities.

As in a MVC structure, data storage and representation, user interface presentation, and control are separated into different layers. The major categories, roughly ordered from “front-end" to “back-end," follow:

- Smarty templates , which are responsible for assembling HTML pages to display to users;
- Page classes , which receive requests from users' web browsers, delegate any required processing to various other classes, and call up the appropriate Smarty template to generate a response;
- Action classes , which are used by the Page classes to perform non-trivial processing of user requests;
- Model classes , which implement PHP objects representing the system's various entities, such as Users, Articles, and Journals;
- Data Access Objects (DAOs) , which generally provide (amongst others) update, create, and delete functions for their associated Model classes, are responsible for all database interaction;
- Support classes , which provide core functionalities, miscellaneous common classes and functions, etc.

As the system makes use of inheritance and has consistent class naming conventions, it is generally easy to tell what category a particular class falls into. For example, a Data Access Object class always inherits from the DAO class, has a class name of the form ``[Something]DAO``, and has a filename of the form ``[Something]DAO.inc.php``.

The following diagram illustrates the various components and their interactions.

