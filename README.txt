// $Id$


******************************************************
WARNING: THIS MODULE IS NOT READY FOR PRODUCTION YET - IT IS STILL "IN DEVELOPMENT"
******************************************************


CONTENTS OF THIS FILE
---------------------

 * Introduction
 * Installation
 * Todos: stuff I want to fix before publishing to d.o


INTRODUCTION
------------

Current Maintainer: Ned <http://drupal.org/user/798324>

Drupal 6 module to send SMS Blasts to bulk lists of numbers. 

Depends on SMS Framework.


The user can either:
 - "Send with form": paste a list of SMS numbers into a HTML form - quick and easy!
 - "Send with Views": select an existing View and CCK field - SMSs will be sent to the number in the CCK field for every node returned by the View.

SMS messages themselves are entered free-form.  There is a "history" log of past SMS Blasts, including per-recipient success/fail status.

The "Send with form" option is really simple and easy to use. 
On the other hand, the "Send with Views" approach is much more powerful and difficult to use.  In order to take advantage of "Send with Views", follow these steps:
 1) Install and enable the Views module (you'll probably want views_ui, too)
 2) Create (or reuse) a Content Type with a CCK field for storing SMS numbers.
     For example, try calling the Content Type "SMSRecipients" and the CCK field "SMSNumber".
 3) Create some test nodes in your content type. 
     Be sure to use 10-digit US SMS numbers in your designated CCK field.
     You can also use the Feeds module to use a CSV file to create a bunch of nodes.
 4) Create (or reuse) a View that returns the nodes you care about. 
     It doesn't matter what fields are included in the view.
     This is where the power comes in.  In the simplest case, you can just create a view that returns all nodes of a specific Content Type.  In the more complex case, you can use Views to filter a specific subset of recipients.  Views provides powerful filtering on arbitrary CCK fields.
 5) Go to the "Send with Views" form.  Select your View, and the CCK field that contains your SMS numbers.  IMPORTANT NOTE: each node returned by the View should contain the CCK field you select, and the fields should all contain valid 10-digit US SMS numbers.  Otherwise, you'll get warnings for the nodes where that's not the case.


INSTALLATION
------------

1. Install as usual, see http://drupal.org/node/70151 for further information.
2. XXX


TODOS: STUFF i WANT TO FIX BEFORE PUBLISHING TO D.O:
-----------------------------------------

  - Lots of todos are marked with "XXX"
  - Rules integration - send blast as a Rules event AND action
  - Fix history for "send with form"  
  - Improve documentation and overview page - esp. for "Send with Views"
  - De-dupe numbers (?)


