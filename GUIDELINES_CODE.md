Submitting a pull request
=========================

Before you submit a pull request, there's a few bits of housekeeping to do.

Submit from a feature branch, not your ``main`` branch
------------------------------------------------------

Before you start working on your change, make sure you've created a branch.
By default, when you clone your repository fork, you'll be checked out on
your ``main`` branch. This is a direct copy of Toga's ``main`` branch.

While you *can* submit a pull request from your ``main`` branch, it's preferable
if you *don't* do this. If you submit a pull request that is *almost* right, the
core team member who reviews your pull request may be able to make the necessary
changes, rather than giving feedback asking for a minor change. However, if you
submit your pull request from your ``main`` branch, reviewers are prevented from
making modifications.

Instead, you should make your changes on a *feature branch*. A feature branch
has a simple name to identify the change that you've made. For example, if
you've found a bug in Toga's layout algorithm, you might create a feature branch
``fix-layout-bug``. If your bug relates to a specific issue that has been
reported, it's also common to reference that issue number in the branch name
(e.g., ``fix-1234``).

To create a feature branch, run:

.. tabs::

  .. group-tab:: macOS

    .. code-block:: console

      (venv) $ git checkout -b fix-layout-bug

  .. group-tab:: Linux

    .. code-block:: console

      (venv) $ git checkout -b fix-layout-bug

  .. group-tab:: Windows

    .. code-block:: doscon

      (venv) C:\...>git checkout -b fix-layout-bug

Commit your changes to this branch, then push to GitHub and create a pull request.

Add change information for release notes
----------------------------------------

Before you submit this change as a pull request, you need to add a *change
note*. Toga uses `towncrier <https://pypi.org/project/towncrier/>`__ to automate
building the release notes for each release. Every pull request must include at
least one file in the ``changes/`` directory that provides a short description
of the change implemented by the pull request.

This description should be a high level summary of the change from the
perspective of the user, not a deep technical description or implementation
detail. It is distinct from a commit message - a commit message describes what
has been done so that future developers can follow the reasoning for a change;
the change note is a "user facing" description. For example, if you fix a bug
caused by date handling, the commit message might read:

    Modified date validation to accept US-style MM-DD-YYYY format.

The corresponding change note would read something like:

    Date widgets can now accept US-style MM-DD-YYYY format.

The change note should be in ReST format, in a file that has name of the format
``<id>.<fragment type>.rst``. If the change you are proposing will fix a bug or
implement a feature for which there is an existing issue number, the ID will be
the number of that ticket. If the change has no corresponding issue, the PR
number can be used as the ID. You won't know this PR number until you push the
pull request, so the first CI pass will fail the Towncrier check; add the change
note and push a PR update and CI should then pass.

There are five allowed fragment types:

- ``feature``: The PR adds a new behavior or capability that wasn't previously
  possible (e.g., adding a new widget, or adding a significant capability to an
  existing widget);
- ``bugfix``: The PR fixes a bug in the existing implementation;
- ``doc``: The PR is an significant improvement to documentation;
- ``removal``; The PR represents a backwards incompatible change in the Toga
  API; or
- ``misc``; A minor or administrative change (e.g., fixing a typo, a minor
  language clarification, or updating a dependency version) that doesn't need to
  be announced in the release notes.

Some PRs will introduce multiple features and fix multiple bugs, or introduce
multiple backwards incompatible changes. In that case, the PR may have multiple
change note files. If you need to associate two fragment types with the same ID,
you can append a numerical suffix. For example, if PR 789 added a feature
described by ticket 123, closed a bug described by ticket 234, and also made two
backwards incompatible changes, you might have 4 change note files:

* ``123.feature.rst``
* ``234.bugfix.rst``
* ``789.removal.1.rst``
* ``789.removal.2.rst``

For more information about Towncrier and fragment types see `News Fragments
<https://towncrier.readthedocs.io/en/stable/tutorial.html#creating-news-fragments>`__.
You can also see existing examples of news fragments in the ``changes``
directory of the Toga repository. If this folder is empty, it's likely because
Toga has recently published a new release; change note files are deleted and
combined to update the :doc:`release notes </background/project/releases>` with
each release. You can look at that file to see the style of comment that is
required; you can look at `recently merged PRs
<https://github.com/beeware/toga/pulls?q=is%3Apr+is%3Amerged>`__ to see how to
format your change notes.

It's not just about coverage!
-----------------------------

Although we're always trying to improve test coverage, the
task isn't *just* about increasing the numerical coverage value. Part of the
task is to audit the code as you go. You could write a comprehensive set of
tests for a concrete life jacket... but a concrete life jacket would still be
useless for the purpose it was intended!

As you develop tests and improve coverage, you should be checking that the
core module is internally **consistent** as well. If you notice any method
names that aren't internally consistent (e.g., something called ``on_select``
in one module, but called ``on_selected`` in another), or where the data isn't
being handled consistently (one widget updates then refreshes, but another
widget refreshes then updates), flag it and bring it to our attention by
raising a ticket. Or, if you're confident that you know what needs to be done,
create a pull request that fixes the problem you've found.

One example of the type of consistency we're looking for is described in
`this ticket <https://github.com/beeware/toga/issues/299>`__.

Waiting for feedback
--------------------

Once you've written your code, test, and change note, you can submit your
changes as a pull request. One of the core team will review your work, and
give feedback. If any changes are requested, you can make those changes, and
update your pull request; eventually, the pull request will be accepted and
merged. Congratulations, you're a contributor to Toga!
