$Id$

DESCRIPTION
===========
When using Workflow and/or Rules this module comes in handy to help you realise
some common use case scenarios and to spruce up your Workflow interface.
As far as the UI goes this module replaces the traditional workflow radio
buttons by single-action buttons featuring context-sensitive labels, using 
replacement tokens, if desired, for a more intuitive user experience.
It also defines some extra tokens that may be used with Rules to invoke actions,
like sending reminder emails, when content was NOT updated or a workflow did NOT
transition state for some time.

Let's say we have a basic workflow with states "draft", "review" and "live".
Traditionally authors and moderators must select the next state by pressing
the correct radio-button and clicking submit. Experience from the field
suggests that not everybody finds this intuitive. Rather than having to think
in terms of state transitions, users prefer to press a button with a an 
explanatory label that clearly expresses what is going to happen.
Using this module authors will find on their edit forms clearly labeled buttons,
for instance "Save as draft, don't submit" and "Submit for publication".
In old workflow-speak "Submit for publication" was represented by radio buttons
plus a submit button which would read less intuitively as: transition workflow
state from "draft" to "review".
Similarly, with this module moderators will see on their edit form buttons
like "Reject and return to author John" (i.e. "review -> draft") and "Publish
this" or "Go live with this!" ("review -> live").

 This module also defines replacement tokens [node:mod-since-seconds] and
 [node:workflow-state-age], which when used in a scheduled rule set, allow you
 to invoke actions when content was NOT updated or a workflow state NOT
 transitioned after a specified elapsed time.
 See http://drupal.org/project/workflow_extensions for full instructions on how
 to do this using Rules.
 Note: Workflow is not required if you're only after [node-mod-since-seconds]
 token.

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
"Edit labels" tab to enter your custom labels. 
With the Token module installed you may use replacement tokens in your custom
labels, for instance:
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
