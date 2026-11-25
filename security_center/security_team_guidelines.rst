Guidelines for Security Team Members
====================================

Pre-setup
---------
All members of all security teams must install and configure PGP/GPG software.
All members must be ready to receive encrypted emails and keep those emails
encrypted during discussion with members of the security aliases or the
reporter. All outbound emails from security team members to other parties
regarding security incidents must be signed with the member's personal key.

All members must generate or use a pre-existing personal key pair. Pre-existing
keys must be at least RSA2048 or equivalent. New keys must be at least RSA4096
or equivalent.

A single "TF Security" key is used for all inbound communication to the Trusted
Firmware security aliases. Only members of security@lists.trustedfirmware.org
own the private part of this key, which is not used for direct communication.
A subkey of this is used for direct communication and the private part of this
subkey is securely shared with all members of all security aliases. Security
team members should sign the public "TF Security" subkey with their personal
key and send that back to security@lists.trustedfirmware.org for wider sharing.

All security team members are responsible for notifying
security@lists.trustedfirmware.org if anyone leaves a security alias,
so that a member of security@lists.trustedfirmware.org can revoke the "TF
Security" subkey and issue a new one.

It is desirable to further expand the web of trust by getting the "TF Security"
public subkey and security team members' personal public keys signed by other
members of the security teams and trusted members of the wider OSS community,
but that is not a pre-requisite of this process.

Triage
------

1. New incident comes into security@lists.trustedfirmware.org.

2. The triager analyses the incident as soon as possible and always within 3
   working days (Monday to Friday in their timezone) of the initial report.

   a. If the incident is obviously not a security vulnerability, the triager
      rejects it, giving the standard rejection response to the reporter with
      specific rejection reasoning.

   b. Otherwise the triager forwards the incident to the appropriate
      project security team(s) if not done already, providing the reporter's
      contact details.

3. In general, security@lists.trustedfirmware.org should not be involved in
   subsequent handling of the incident but it may act as an escalation point
   if handling by the project security team(s) is not functioning properly.


Project handling
----------------
(All responses to the reporter should cc
*<project>-security@lists.trustedfirmware.org*).

1. New incident comes into *<project>-security@lists.trustedfirmware.org*.

2. Someone on *<project>-security@lists.trustedfirmware.org* immediately
   replies to the list to say they will be the project incident handler.

3. The project incident handler analyses the incident as soon as possible and
   always within 7 days of receipt. They create a new "security-incident" in
   the project's issue tracker. They may pull in other project security team
   members or trusted contributors to the project to help with the analysis but
   access to this information must be restricted to this group.

   a. If the incident is deemed not a security vulnerability [#f1]_, the project
      incident handler rejects it, giving the standard rejection response to
      the reporter with specific rejection reasoning. If the incident is a
      normal bug, the project incident handler reports one via the project's
      normal bug reporting process. They close the "security-incident" task.

   b. Otherwise the project incident handler accepts the incident is (or may
      be) a security vulnerability and proceeds to the next stage.

4. The project incident handler consolidates the information gathered on the
   (potential) vulnerability so far and shares that information with the
   reporter [#f2]_. As part of this communication, it's possible that the
   (potential) vulnerability is downgraded to a normal bug. For confirmed
   vulnerabilities, the project incident handler arranges for someone to fix
   the vulnerability and at a lower priority, request a CVE from Linaro and
   optionally begin drafting a security advisory. They must ensure that any
   sensitive information the reporter provides is stripped out before
   communication outside the security teams.

5. The project incident handler is responsible for negotiating
   embargo/disclosure timelines with the reporter [#f2]_ and Trusted
   Stakeholders, and keeping them informed throughout the remainder of the
   process.

6. After a fix for the vulnerability is available, the project incident handler
   shares the fix and latest vulnerability information with the reporter [#f2]_
   and *<project>-trusted-stakeholder-notify@lists.trustedfirmware.org*. The
   fix embargo period starts.

   If the project is not allowed to distribute the fix privately due to export
   control restrictions, there is no fix embargo period but
   *<project>-trusted-stakeholder-notify@lists.trustedfirmware.org* should
   still be notified before public release, to enable them to prepare for fix
   deployment. 

7. When the fix embargo period ends, the project incident handler
   arranges for the vulnerability fix to be made public.

8. The project incident handler arranges for someone in the project to publish
   a CVE and optionally a security advisory.


.. rubric:: Footnotes

.. [#f1]
   Each project may have its own process for determining this. This may include
   a threat model, severity scoring of the bug and a bug bar for determining
   which bugs should be treated as security vulnerabilities. For projects that
   use severity scoring, CVSSv3 is preferred to align with Mitre CVEs.

.. [#f2]
   By default, sensitive information includes the reporter's identity, their
   organization and their organization's product information. The reporter may
   specify other sensitive information.

