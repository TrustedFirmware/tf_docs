Frequently Asked Questions
==========================

Security issues
---------------

Q: Unauthenticated Jenkins Server
*********************************
   - The domains listed below are available to unauthenticated users. This is
     deliberate and poses no security issues. There are no privileged builds
     with confidential information logged. Jenkins is configured to hide secrets
     from output and logs. If you still come across non-open source content or
     other content that you believe is sensitive, please let us know what that
     content is and why you believe it's sensitive and then we will investigate
     further.

     **Domains**
      - https://ci.trustedfirmware.org
      - https://ci.staging.trustedfirmware.org

Q: I found a security issue in product X, will you fix it?
**********************************************************
   - If the product uses source code from TrustedFirmware's open source
     projects, then yes. However, if the product was made by a third party who
     built on TrustedFirmware technologies but modified the source code, we
     recommend contacting the company behind the product instead. Ideally, they
     should fix their product and provide updates to the corresponding upstream
     tree if the issue affects open and upstream code. In this case, we believe
     that the company behind the product interacts directly with the
     TrustedFirmware security incident team as well.


Bug bounty
----------

.. _bug_bounty:

Q: Do you have a bug bounty program?
************************************
   - TrustedFirmware does not currently operate a bug bounty program. All
     projects within TrustedFirmware are Open Source and sustain their
     operations through contributions from diverse entities, including
     companies, organizations, individuals, researchers, freelancers and
     hobbyists. Some contribute financially, while others provide engineering
     resources, hardware and infrastructure. Due to all work being done in the
     open, we believe security incident work should be treated the same, but of
     course with the difference that reporting is following the process as
     described in the :ref:`psirt_process`.


Q: I reported a security issue, how do I get my bounty?
*******************************************************
   - Please see :ref:`bug_bounty`.

Q: I found a security issue, but will only let you know if you pay me.
**********************************************************************
   - Unfortunately, we cannot do much. TrustedFirmware runs open source projects
     and relies on contributions as described here :ref:`bug_bounty`.
