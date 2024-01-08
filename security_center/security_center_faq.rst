Security Center Frequently Asked Questions
==========================================

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
   - If the product uses source code from TrustedFirmware's open source projects
     as is, then yes. Regardless we always recommend to also invoke the PSIRT
     team at the company behind the product as well.

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
     described in the :doc:`incident_handling_process`.

Q: I found a security issue, but will only let you know if you pay me.
**********************************************************************
   - Unfortunately, we are unable to handle requests like this. TrustedFirmware
     runs open source projects as described in the previous question in this
     FAQ.
