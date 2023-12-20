Trusted Firmware Project Maintenance Process
============================================

Goal of this document
---------------------
As the developer community at http://trustedfirmware.org is growing, there is
an increasing need to have work processes that are clearly documented, feel
smooth and scale well. The aim of this document is to define a set of rules,
guidelines and processes to try and improve the way we work together as a
community today. In particular, some of these goals are:

* To make the code review process more explicit and clearly documented.
* To set expectations for contributors and reviewers.
* To establish a hierarchy of roles and their responsibilities.
* To provide guidelines for new contributors.
* To enlarge maintainership to developers outside of Arm.

We hope that it will make it easier for people to contribute to the projects,
improve the time it takes to get patches merged in the tree, make the process
more transparent, while reducing potential frictions and frustration that can
arise in the community.

This document applies to the TF-A and TF-M projects currently but might be
extended to other http://trustedfirmware.org projects in the future.

Definitions of roles, rights and responsibilities
-------------------------------------------------
There are several roles that people contributing to the project can assume.
Different roles come with different rights and responsibilities and are
attributed based on the level of expertise and engagement in the project, the
bandwidth, to name a few.

Contributor
^^^^^^^^^^^
Default role for anyone starting to contribute to the project.

Contributors may:

* Submit patches for review with an aim to get them merged upstream.
* Review other people's patches. Although their valuable input is always
  welcome, it is not sufficient to get a patch approved and merged. Similarly,
  they can express concerns but these cannot veto a patch. See section
  :ref:`patch_lifecycle_label`.
* Participate on the development mailing list.

Code Owner
^^^^^^^^^^
Someone who looks after a particular module of the source tree (for example,
the power management layer or a specific platform port.)

The project keeps a list of code owners, their contact information along with
the modules they manage. Ideally, every module in the code base should have a
dedicated code owner, as orphan modules are likely to break over time.

Code owners will get requested to review patches in the modules they own and
they are responsible to do so in a timely manner. If several code owners are
looking after the same module, each patch needs only approving by one of them
(but more of them might do it if they wish). A code owner must have a genuine
interest in the said module and have enough bandwidth to deal with incoming
reviews and general design discussions.

Maintainer
^^^^^^^^^^
There are a number of maintainers assigned to the project. The project keeps a
list of them along with their contact information. Maintainers don't
necessarily need a deep domain expertise of all areas of the project; instead
they look at the project from a high level perspective. They must ensure that
changes adhere to the project's quality criteria, to its architectural
direction, to its threat model and so on.

Code owners and maintainers are complementary roles.

Unlike code owners, maintainers may approve any patch, no matter what module it
concerns. They are responsible for ensuring patches have had enough overall
review and adding their own approval in a timely manner.

They also have merge rights, i.e. the ability to merge a patch in the tree once
it has received all required approvals.

Note that roles can be cumulative, in particular the same individual may be
both a code owner and a maintainer.

How to become a code owner?
^^^^^^^^^^^^^^^^^^^^^^^^^^^
Usually, the individual contributing a new major piece of code to the project
naturally becomes the code owner for this module. Such a major contribution
should be accompanied by an update to the list of code owners.

It is strongly discouraged to contribute a major piece of code and not nominate
yourself (or someone you know and work with) as the code owner for it, as then
there is no one to look after this module with the right expertise.

For existing code that already has a code owner (or several), if you wish to
help you may propose that you become an additional code owner for this module.
To do this, add yourself to the list of code owners and submit the resulting
patch for review, adding all other code owners for this module as reviewers.
At least 2 existing code owners (or 1 if there is a sole code owner) must
approve it and none of them veto it.

How to become a maintainer?
^^^^^^^^^^^^^^^^^^^^^^^^^^^
Maintainers are elected by their peers on a meritocracy basis.

To be assigned as a maintainer, you need to satisfy the criteria set by the
project. This typically covers things like:

* Being an active member of the project for a minimum duration.
* Having contributed a substantial number of non-trivial and high-quality
  patches
* Having reviewed a substantial number of non-trivial patches, preferably in
  the generic layer, with high-quality constructive feedback.
* Behaving in a professional and polite way, with the best interests of the
  project at heart.
* Showing a strong will to improve the project and to do the right thing,
  rather than going for the quick and easy path.
* Participating in design discussions on the development mailing list.
* Having appropriate bandwidth to deal with the workload.

.. _patch_lifecycle_label:

Life Cycle of a Patch - From submission to integration in the tree
------------------------------------------------------------------
All the above roles play a part in the life cycle of a patch. This section
outlines who needs to do what in order for a patch to be approved and merged.

When posting a new patch for review, a contributor (and patch author) must
choose his reviewers. A patch must be approved by:

* At least 1 code owner for each module modified by the patch.
* At least 1 maintainer.

Thus the patch author should assign the right reviewers to reach this target.
Reviewers may add other reviewers, and they may also add some non-code owners
if they think they might provide useful input (for example because of their
past work and experience). Appropriate code owners might be found by looking at
the list of code owners for the project. Similarly for maintainers. For
additional non-code owners, it is also useful to run a "git blame" on the
source code to find out who's been recently working on this area of the code.

The patch author is responsible for addressing all review comments from all
code owners and maintainers, until they approve the patch.

Addressing a comment might mean 2 things, depending on the nature of the
comment:

* Questions are addressed by providing an answer.
* Suggestions can be addressed in one of 3 ways:

  * Adopt it immediately and post the reworked version.
  * Defer it to a subsequent change. The patch author is then responsible for
    making sure it gets done at some point in the future.
  * Disagree and provide additional info to explain your approach.

Once a patch has been approved by all relevant code owners and maintainers, it
may be merged.

In case of disagreement between the different parties involved in the review,
leading to a stalemate situation where the patch cannot progress further,
a third-party maintainer should be contacted to settle the case.

It is important to note that the patch author is responsible for driving their
review. In particular, they should not expect that people will review their
patches if they don't request them to do so. On the other hand, once someone
has been asked to review a patch, they should do so in a timely manner, or if
they don't have the bandwidth to do it currently, they should say so
explicitly. In this case, the patch author should look for another appropriate
reviewer.

Patch Contribution Guidelines
-----------------------------
Here are some general guidelines all patches are expected to comply with. 

* Keep patches small, split them in logical units. Keep them on topic. If you
  need to fix another bug or make another enhancement, please push them into a
  separate patch.
* Write informative and comprehensive commit messages. A good commit message
  provides all the background information needed for reviewers to understand
  the intent and rationale of the patch. This information is also useful for
  future reference.
* The patch compiles without any warnings for all supported configurations.
* The patch meets the project's code quality criteria.
* The patch adheres to the project's coding style.
* The documentation has been updated accordingly.
* The continuous integration (CI) system has been updated accordingly (or will
  shortly be after the code updates).
* The patch has been tested as per the testing requirements of the project.
  In particular, it passes all CI tests, does not introduce any regression and
  does not break existing code. In the case where the required tests have not
  been integrated in the CI just yet, additional targeted testing has been
  locally conducted and details of that (list of tests and results) have been
  made available.

These apply as much to generic code as to platform code.

These general guidelines might be extended or refined by projects.

Platform Support Life Cycle
---------------------------
Maintaining a platform essentially consists of keeping up to date the following
items:

* Documentation.
  Platform documentation should typically describe the hardware, what features
  in the project are supported on this platform, how they are configured and
  how to use them.
* Build support.
  All supported configurations should build cleanly.
* Continuous integration (CI) system.
  Proper testing for this platform should be deployed in the CI and maintained
  over time.

This is a lot of work and it is unreasonable to expect in an open source
project that all platforms are supported forever. The following stages of
a platform's life cycle are defined as a way to manage that.

Fully Supported
^^^^^^^^^^^^^^^
A fully supported platform needs to meet the following requirements:

* It builds with all the versions of toolchains supported by this platform.
* It builds all the configurations supported by this platform.
* All supported configurations are tested in the CI and all tests pass.
* The documentation is up to date (in particular the list of supported
  features).

Note that it is acceptable for some of these items to be temporarily broken or
out of date, so long as they are clearly tracked by tickets.

Limited Support
^^^^^^^^^^^^^^^
The platform is supported to some degree but not every criteria of a "fully
supported" platform is satisfied. For example, some build configurations fail,
or some tests fail, or the platform does not have a fully functional, complete
CI loop yet.

The documentation should still clearly state what's known to work and what's
broken.

What does not work will be disabled in the CI to keep it healthy and useful to
everyone.

This should be a temporary state until the platform is brought back into
"fully supported" state. If the situation does not improve, it will become
"deprecated" after some time.

Deprecated
^^^^^^^^^^
The platform is no longer supported. It could be because it has reached its
end of life or there is a lack of interest in the community.

Deprecated platforms may be removed from the codebase in future.

Per-project guidelines
----------------------
This document outlines the general expectations for all
http://trustedfirmware.org projects. In most cases, projects would typically
extend and/or refine these in a complementary document.

Such project guidelines would typically cover the following topics (this list
is not exhaustive):

* Code review timelines (for example, defining that "All patches must be
  reviewed in a *timely* manner").
* Code review guidelines.
* Documentation guidelines.
* Testing standards.
* Code of conduct (on top of the `Trusted Firmware Code of Conduct`_). Among
  other things, this would define a way to measure maintainers and code owners
  inactivity and how to give them notice that their roles might be revised if
  they don't resurface, or warn them about impending life cycle state changes.
* Deprecated platforms policy (e.g. keep them forever in the tree for
  reference, remove them after some time, ...)
* A process to document the list of features in the project and their level of
  support for each platform.
* Define standard labels for the ticketing system (per
  platform/feature/version/...).
* Branching strategies.

Exclusions and complementary notes
----------------------------------
There are things we thought about but did not include in this document on
purpose. They are listed below for completeness.

* We will most likely need a deviation to the code review process for patches
  that need to be fast-tracked. This should only apply in some circumstances
  and will depend on the nature of the patch.
* In the future, we'll most likely need to organize "key signing" type of
  events to enforce the legitimacy of maintainers and code owners to the tools,
  i.e. to prove that they really are who they claim to be and protect our tree
  from user identity spoofing.
* The list of code owners and maintainers for the project might be provided in
  a file in the source tree. A common file for both is likely to be the more
  convenient solution. In the future, it might be worth developing some tools
  (or reusing existing ones if the license is compatible) to assist developers
  (for example suggesting specific code owners or maintainers based on the
  nature of the patch).
* For both TF-A and TF-M, the CI system is not quite ready to be extended by
  the community. Thus, some of the guidelines around adding the required level
  of testing in the CI cannot be applied right now. We hope the situation will
  quickly evolve, which is why it's been included in this document nonetheless.
* In the future this document might be expanded to address multi-branch
  maintainership.

Versions and history
--------------------

+---------+------------+--------------------------------------------------+
| Version | Date       | Changes                                          |
+=========+============+=========+========================================+
| 1.0     | 11/05/2020 | First version.                                   |
+---------+------------+--------------------------------------------------+
| 1.1     | 20/12/2023 | Migrated to rst format. Minor grammatical fixes. |
+---------+------------+--------------------------------------------------+


.. _Trusted Firmware Code of Conduct : https://www.trustedfirmware.org/coc/
