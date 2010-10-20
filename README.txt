$Id$

DESCRIPTION
===========
This module replaces the traditional workflow radio-buttons by single-action 
buttons featuring context-sensitive labels (using replacement tokens) for a more
intuitive user experience.

Let's say we have a basic workflow with states "draft", "review" and "live".
Traditionally authors and moderators must select the next state by pressing
the correct radio-button and clicking submit. Experience from the field
suggests that not everybody finds this intuitive. Rather than having to
think in terms of state transitions, users prefer to press a button with a
an explanatory label that clearly expresses what is going to happen.
Using this module an author, say John, may find on the page edit form a couple
of buttons labeled "Save as draft, don't submit" (no state transition, stays 
in "draft") and "Submit for publication" (i.e "draft -> review").
A moderator may see on the edit form buttons like "Reject and return to John" 
(i.e. "review -> draft"), "Publish this page" ("review -> live") and "Unpublish 
this page".

INSTALLATION
============
Installation is like any other module. Uncompress the .tar.gz file and drop it 
into the "sites/all/modules" subdirectory.
Visit Administer >> Site building >> Modules, tick the box in front of the
module name and press "Save configuration".
Or use drush.
For full control over the labels to put on your workflow buttons also install
Workflow Named Transitions.

CONFIGURATION
=============
If you have Workflow Named Transitions installed (highly recommended), visit 
Administer >> Site building >> Workflow and click the "Edit labels" tab to enter
custom labels. You may use tokens, e.g.:
  "Reject submission, return to [author-name]" or 
  "Transition to [workflow]:[workflow-new-state-name]"
In addition, there are a couple of self-explanatory configuration options at
Administer >> Site configuration >> Workflow extensions.

USAGE
=====
Users will find that the workflow radio buttons previously used to instigate
state transitions are now replaced by more intuitive single-action buttons
labeled with the texts you entered above. This applies the the node edit and
comment forms, as well as the Workflow tab (node/%/workflow, if enabled at
Administer >> Site building >> Workflow >> edit, section "Workflow tab 
permissions").

UNINSTALL
=========
Disable and uninstall as per normal at Administer >> Site building >> Modules.
