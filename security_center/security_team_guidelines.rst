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
(All responses to the reporter should cc security@lists.trustedfirmware.org)

1. New incident comes into security@lists.trustedfirmware.org.

2. Someone on security@lists.trustedfirmware.org replies to the list
   as soon as possible to say they will be the triager for the incident. This
   should preferably be the representative for the relevant project but can be
   another member. 

3. The triager analyses the incident as soon as possible and always within 3
   working days (Monday to Friday in their timezone) of the initial report.

   a. If the incident is obviously not a security vulnerability, the triager
      rejects it, giving the standard rejection response to the reporter with
      specific rejection reasoning.

   b. Otherwise the triager accepts the incident, giving the standard holding
      response to the reporter. They forward the incident to the appropriate
      *<project>-security@lists.trustedfirmware.org* if not done already.

   In some cases the incident may affect more than one project; in such cases
   the triager should act as the reporter's point of contact for the incident.
   If the incident only affects one project, the project incident handler
   (see below) is the point of contact. If the relevant project(s) are not
   clear then the triager pulls in other members of
   security@lists.trustedfirmware.org or the project security teams
   as appropriate until this is determined.
    
4. The triager is responsible for ensuring the relevant project security team
   is handling the process as defined here in a timely manner. They should also
   act as the reporter's backup point of contact if the project security team
   is not functioning properly.

5. The other members of security@lists.trustedfirmware.org are responsible for
   picking up the duties of the triager if the triager becomes unavailable.


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

   a. If the incident is deemed not a security vulnerability^^, the project
      incident handler rejects it, giving the standard rejection response to
      the reporter with specific rejection reasoning. If the incident is a
      normal bug, the project incident handler reports one via the project's
      normal bug reporting process. They close the "security-incident" task.

   b. Otherwise the project incident handler accepts the incident is (or may
      be) a security vulnerability and proceeds to the next stage.

4. The project incident handler consolidates the information gathered on the
   (potential) vulnerability so far and shares that information with the
   reporter^^^ and *<project>-ess-notify@lists.trustedfirmware.org* (if
   applicable to project). As part of this communication, it's possible that
   the (potential) vulnerability is downgraded to a normal bug. For confirmed
   vulnerabilities, the project incident handler arranges for someone to fix
   the vulnerability and as a lower priority, someone to begin drafting a
   security advisory. They must ensure that any sensitive information^ the
   reporter provides is stripped out before communication outside the security
   teams. They should also request a CVE from Mitre at this stage if not
   already done by the reporter.

5. The project incident handler is responsible for negotiating
   embargo/disclosure timelines with the reporter^^^ and stakeholders, and
   keeping them informed throughout the remainder of the process. Triggers for
   new updates include: new vulnerability fix available, new advisory draft
   available, fix/advisory becoming public, vulnerability status change (e.g.
   severity changed, new exploit found, change in disclosure plan, ...).

6. After a fix for the vulnerability is available, the project incident handler
   shares the fix with the reporter^^^ and
   *<project>-ess-notify@trustedfirmware.org* via email (unless the projects
   is not allowed to distribute the fix due to export control restrictions). If
   an embargo is agreed with an ESS, the primary embargo period starts.

7. After the primary embargo period (if applicable) ends, the project incident
   handler notifies
   *<project>-trusted-stakeholder-notify@lists.trustedfirmware.org* with the
   latest information and keeps them informed throughout the remainder of the
   process. The secondary embargo period starts.

8. When the secondary embargo period ends, the project incident handler
   arranges for the vulnerability fix to be made public (unless public fix
   release is deferred - see :doc:`incident_handling_process`.

9. The project incident handler circulates drafts of the security advisory with
   the reporter, ESSes and Trusted Stakeholders as they become available.

10. When the public embargo period ends, the project incident handler arranges
    for the advisory (and vulnerability fix if not done before) to be made
    public.


^ By default, sensitive information includes the reporter's identity, their
organization and their organization's product information. The reporter may
specify other sensitive information.

^^ Each project may have its own process for determining this. This may include
a threat model, severity scoring of the bug and a bug bar for determining
which bugs should be treated as security vulnerabilities. For projects that
use severity scoring, CVSSv3 is preferred to align with Mitre CVEs.

^^^ Or triager for incidents that affect multiple projects since they are the
point of contact.
