Security Incident Handling Process
==================================

Reporting
---------

If you think you have found a security vulnerability, then please send an email
to the Trusted Firmware security team at security@lists.trustedfirmware.org.
You may also use the project specific security team aliases
:doc:`here <mailing_aliases>`. These are private teams of security officers
who will help verify the security vulnerability, develop and release a fix,
and disclose the vulnerability details responsibly. The security teams are
referred to from now on as "us/we/our". We do our best to respond and fix any
issues as soon as possible.

As with any bug, the more information you provide, the easier it is to diagnose
and fix. If you already have a fix, please include it with your report, as that
can speed up the process considerably. Any exploit code is very helpful. We may
bring in extra help from area maintainers to understand and fix the
vulnerability.

Please let us know your disclosure plans if you have any. This may affect our
disclosure plan as described in the next section.

Please indicate any sensitive information you do not wish us to share. We
reserve the right to share any information you provide with trusted third
parties and eventually the public unless you request otherwise. We will credit
you in any security advisory unless you request otherwise.

You may use :download:`this PGP/GPG key <pub_security_at_trustedfirmware_subkeys_3.asc>`
for encrypting the vulnerability information. This key is also available at
https://keyserver.pgp.com and LDAP port 389 of the same server. The
fingerprint for this key is:

54F8 6138 58DB 00F2 2EE7 D559 EB2C 1B71 C010 2B2B

If you would like replies to be encrypted, please provide your public key.
Please note we cannot guarantee that encrypted information will remain
encrypted when shared with trusted third parties.

If we consider the bug not to be a security vulnerability, we will inform you
and direct the bug to the normal bug fixing process.

Disclosure
----------
Our default security vulnerability disclosure plan is as follows. This may
change if disclosure needs to be coordinated with the reporter or other
stakeholders.

1. For confirmed security vulnerabilities, we will develop a robust fix as soon
as possible. During this time, we will only share information with the
reporter, those needed to develop the fix and Especially Sensitive Stakeholders
(ESSes). See the :ref:`ts_registration_label` section for more information
about ESSes and Trusted Stakeholders. If the fix is particularly difficult to
implement, we may proceed to subsequent steps without a fix.

2. After a robust fix becomes available, our preference is to publicly release
it as soon as possible. We will automatically do this if the vulnerability is
already publicly known.

Security fixes should contain the minimum information required to fix the bug.
We will usually publicly disclose the corresponding vulnerability details
later, on the public disclosure date (see step 5 below).

We may defer public release of the fix if the reporter requests it or we think
the fix contains enough information for a skilled attacker to re-construct
the exploit. In this case we will publicly release the fix on the public
disclosure date. This will not prevent the fix from being shared with ESSes
and Trusted Stakeholders before public disclosure (but see export control
restriction below).

We may also defer public release of the fix if an ESS requests it within 1
calendar day of being notified and we agree the criticality of the
vulnerability requires more time. The ESS requested deferral period should be
as short as possible, up to 7 calendar days after the fix becomes available,
with an exceptional extension to 14 calendar days. The only valid reason for
release deferral is to accommodate deployment of the fix by ESSes. If it is
immediately clear that ESSes are unaffected by the vulnerability then we will
skip this stage. This 0-14 day deferral is the primary embargo period.

Due to export control restrictions, some Trusted Firmware projects may not be
allowed to distribute the fix privately. For such projects, if an ESS requests
it, we may allow ESSes a reasonable extension to the primary embargo period to
develop and deploy their own fix. This period should be as short as possible
and must always allow enough time for Trusted Stakeholders to develop and
deploy their own fixes before public disclosure.

3. After the primary embargo period, we will share the fix (where possible)
and relevant vulnerability information with registered Trusted Stakeholders.
We may defer fix release further if a Trusted Stakeholder requests it within 3
working days of being notified (Monday to Friday, in their time zone), and we
agree the criticality of the vulnerability requires more time. The requested
deferral period should be as short as possible, up to 7 calendar days after
the Trusted Stakeholder is notified, with an exceptional extension to 14 days.
The only valid reason for further release deferral is to accommodate deployment
of the fix by a Trusted Stakeholder. This further 3-14 day deferral is the
secondary embargo period.

For Trusted Firmware projects that are not allowed to distribute the fix
privately due to export control restrictions, if a Trusted Stakeholder requests
it, we may allow Trusted Stakeholders a reasonable extension to the secondary
embargo period to develop and deploy their own fix. This period should be as
short as possible and must always complete before the public disclosure date. 
In this case the fix will be publicly released after the secondary embargo
period.

4. After fix implementation, we will consolidate details of the security
vulnerability into a security advisory. This includes a CVE number and we will
request one if not already done by the reporter. We will circulate drafts of
the security advisory with the reporter, ESSes and Trusted Stakeholders if they
contain significant updates to earlier notifications.

5. At the agreed public disclosure date, by default 90 days after the
vulnerability was reported, we will publicize the final security advisory and
fix (if not already available) at https://www.trustedfirmware.org/security. This
window from reporting to public disclosure is the public embargo period.

.. _embargoed_info_label:

Handling embargoed information
------------------------------
On receipt of embargoed information, you must not disclose any of the provided
information beyond the group of people in your organization that need to know
about it. During the primary and secondary embargo periods, that group of
people should be limited to those entrusted to assess the impact of the
vulnerability on your organization and deploy fixes to your products. After
the secondary embargo period but during the public embargo period, that group
of people may be expanded in order to prepare your organization's public
response. The embargoed information must not be shared outside your
organization during the public embargo period under any circumstances. It is
permitted to point others to a public fix during an embargo period, as long as
the vulnerability details are not leaked.

If you think another individual/organization requires access to the embargoed
information, then please ask them to :ref:`register <ts_registration_label>`
as a Trusted Stakeholder. If you believe there has been a leak of embargoed
information then please notify us immediately.

We welcome feedback on embargoed information at any time.

.. _ts_registration_label:

Trusted Stakeholder registration
--------------------------------
The security team of each Trusted Firmware project maintains a private, vetted
list of organizations and individuals who are considered Trusted Stakeholders
of security vulnerabilities for that project. Trusted Stakeholders are
organizations impacted by security vulnerabilities found in a Trusted Firmware
project and thus need to be informed before public disclosure.

If you want to register as a Trusted Stakeholder, please contact the relevant
security team alias(es) as listed :doc:`here <mailing_aliases>`, providing the
following information:

1. Which Trusted Firmware project(s) you want to register for.

2. A justification of why you should be on the list. That is, why you should
know about security vulnerabilities and have access to security fixes before
they are made public. For example, a valid reason is that your organization
has deployed products using Trusted Firmware that may need to be patched.

3. Your full name and a valid email address. This should be an organization
email address where possible. We prefer individuals in each organization t
coordinate their registration requests with each other and to provide us with
an email alias managed by your organization instead of us managing a long list
of individual addresses.

4. Confirmation that you and the individuals in your organization will handle 
embargoed information responsibly as described in the
:ref:`embargoed_info_label` section.

Where applicable, the project security teams also maintain an
**E**specially **S**ensitive **S**takeholder (**ESS**) list. This list is
strictly limited to those organizations that use Trusted Firmware for large
scale deployments providing bare-metal access on multi-tenancy systems, and
organizations that supply Trusted Firmware to such deployments. You may use
the same email address above to register for this list but in almost all cases
we expect the Trusted Stakeholder list to be used instead.

Note, we reserve the right to deny registration or revoke membership to the
stakeholders lists, for example if we have concerns about the confidentiality
of embargoed information.
