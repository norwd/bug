# Bug

*Bug* is a simple todo-tracking system for the unix commandline.
It's written in POSIX sh, and it only requires the typical Unix utilities: grep, cut, tr, ...
It should probably work with a small busybox.
The lack of dependencies was the biggest motivation for its development.

Its database format is a text file containing simple tabbed columns which can be even hand-edited.
It uses $EDITOR for submitting or editing the issues and for changing states or priorities.
It relies on four fixed fields: ID, Priority, State, and Subject.
There is also a fifth free-text field for any other information you may want to store about the issue.
There is no database locking or notifications, so it's mostly for tracking the user's own issues.

You can look at a screenshot if you want.

![bug-shot.png](https://viric.name/soft/bug/bug-shot.png)

Download the latest version (GPL 2 or later licensed): bug.gz - v1.1 (The manual is in the header of the file)

Look at the version repository if you are interested in its development.

## Manual

Copy of the manual at v1.1

```sh
# Instructions:
#  1. Your $BUG_PROJECT should point to a file. It will be the database you'll
#     be using. Use an absolute path. It may be, for instance, "~/todo.bug"
#
#  Having the $BUG_PROJECT set:
#  1. Create the database:
#      bug create
#  2. Add an issue
#      bug add
#     Use integers for the priorities. Higher -> more priority.
#     Use any words you prefer for the state
#     Don't break the number of lines until "-- Description --". Write
#     multilines only below that label.
#  3. List the issues (all but description, priority sorted)
#      bug list [ | grep as_you_wish ]
#  4. View an issue
#      bug view 
#  5. Edit an issue
#      bug edit 
#     Change the state, the priority, add data as long as you fix it, ...
#     When I consider an issue is fulfilled, I negate its priority.
#  6. Delete an issue
#      bug delete 
#     Do that whenever you will not need the issue anymore.
#
```

Author: Lluís Batlle i Rossell, viric_at_vicerveza_dot_homeunix_dot_net
