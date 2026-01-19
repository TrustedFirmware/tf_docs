Security Center Frequently Asked Questions
==========================================

Q: How do I report a security issue in your infrastructure?
-----------------------------------------------------------
The Trusted Firmware instrastructure is hosted by Linaro so please follow the
`Linaro security policy <https://www.linaro.org/vdp>`__ (also referred to by
Linaro's `security.txt <https://www.linaro.org/.well-known/security.txt>`__).
Please read the FAQ there before reporting new issues.

Q: I found a security issue in product X, will you fix it?
----------------------------------------------------------
If the product uses source code from TrustedFirmware's open source projects as
is, then yes. Regardless, we always recommend to invoke the PSIRT team at the
company behind the product as well.

Q: Do you have a bug bounty program?
------------------------------------
Yes, Arm operates a bug bounty program on behalf of TrustedFirmware for the
following projects:

* Trusted Firmware-A (TF-A)
* Trusted Firmware-M (TF-M)
* OP-TEE
* Mbed TLS & TF-PSA-Crypto.

Other Trusted Firmware projects are out of scope for now.

If you identify issues in the in-scope projects, you can report them to the bug
bounty program through the
`Intigriti <https://app.intigriti.com/programs/arm/trustedfirmware/detail>`__
platform. Reports will be jointly assessed by Arm's Product Security Incident
Response Team (PSIRT) and the Trusted Firmware security team, with qualifying
issues being eligible for financial rewards based on severity and impact. Please
read the participation guidelines and scope details there before submitting your
report.

If you do not wish to report your security issue through the bug bounty program,
or if the issue does not qualify for the program, please follow the process as
described in the :doc:`incident_handling_process`.

Q: I found a security issue, but will only let you know if you pay me.
----------------------------------------------------------------------
If this affects one of the projects included in the Trusted Firmware bug bounty
program as described in the previous question in this FAQ, you are free to
report it through the Intigriti platform. However, please note that financial
rewards are not guaranteed, as Arm reserves the right to change the severity
of the issue or classify it as a non-security issue, based on its technical
assessment.

If this affects another project, we are unfortunately unable to handle requests
like this.
