Mbed TLS Security
=================

Reporting Process
-----------------

If you think you have found an Mbed TLS security vulnerability, then please
send an email to the security team at
mbed-tls-security@lists.trustedfirmware.org. For more information on
the reporting and disclosure process, please see the
:doc:`incident_handling_process`. There are some caveats to that process when
applied to Mbed TLS, as listed below:

#. Mbed TLS currently does not have any registered ESSes and so there is no
   primary embargo period.
#. Mbed TLS contains strong cryptography software and to comply with export
   control restrictions, must only distribute software publicly. As a result,
   security fixes cannot be shared privately with Trusted Stakeholders, although
   other vulnerability information may be.
#. The nature of Mbed TLS often means that security fixes reveal enough
   information for a skilled attacker to re-construct the originally reported
   exploit. This combined with the previous caveat means we often expect to
   have to withhold security fixes until the public disclosure date.
#. Mbed TLS is subject to a lot of scrutiny by security researchers who often
   have their own disclosure timelines when reporting vulnerabilities. As a
   result, the default 90 days public embargo period may often not apply.

Advisories
----------
Mbed TLS security advisories are available `here <mbed_tls_advisories_>`__.


.. _mbed_tls_advisories: https://mbed-tls.readthedocs.io/en/latest/tech-updates/security-advisories/
