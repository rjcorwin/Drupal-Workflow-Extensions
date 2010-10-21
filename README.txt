$Id$

DESCRIPTION
===========
This module replaces the traditional workflow radio-buttons by single-action 
buttons featuring context-sensitive labels (using replacement tokens) for a more
intuitive user experience.
It also defines some tokens that when used with Rules allow you to take action
when content has NOT been changed or has not transitioned state within a 
specified elapsed time.

Let's say we have a basic workflow with states "draft", "review" and "live".
Traditionally authors and moderators must select the next state by pressing
the correct radio-button and clicking submit. Experience from the field
suggests that not everybody finds this intuitive. Rather than having to
think in terms of state transitions, users prefer to press a button with a
an explanatory label that clearly expresses what is going to happen.
Using this module authors will find on the edit form clearly labeled buttons,
for instance "Save as draft, don't submit" and "Submit for publication".
In old workflow-speak "Submit for publication" was represented by radio buttons
plus a submit button which would read less intuitively as: transition workflow
state from "draft" to "review".
Similarly, with this module moderators will see on their edit form buttons
like "Reject and return to author John" (i.e. "review -> draft") and "Publish
this" or "Go live with this!" ("review -> live").

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
If you have Workflow Named Transitions installed (highly recommended for full
flexibility), visit Administer >> Site building >> Workflow and click the 
"Edit labels" tab to enter custom labels. 
With the Token module installed you may use replacement tokens in your labels, 
for instance:
  "Reject submission, return to [author-name]" or 
  "Transition to [workflow]:[workflow-new-state-name]"

In addition, there are a couple of self-explanatory configuration options at
Administer >> Site configuration >> Workflow extensions.

USAGE
=====
Users will find that the workflow radio buttons previously used to instigate
state transitions are now replaced by more intuitive single-action buttons
labeled with the texts you entered above. This applies to the node edit and
comment forms, as well as the Workflow tab, node/%/workflow, if enabled at
Administer >> Site building >> Workflow >> edit, section "Workflow tab 
permissions".

UNINSTALL
=========
Disable and uninstall as per normal at Administer >> Site building >> Modules.
