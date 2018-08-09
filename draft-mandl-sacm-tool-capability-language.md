---
title: Security Automation and Continuous Monitoring (SACM) Tool Capability Language
abbrev: SACM TCL
docname: draft-mandl-sacm-tool-capability-language-latest
stand_alone: true
ipr: trust200902
area: Security
wg: SACM Working Group
kw: Internet-Draft
cat: info
coding: us-ascii
pi:
  toc: yes
  sortrefs: yes
  symrefs: yes

author:
- ins: A. Montville
  name: Adam W. Montville
  org: Center for Internet Security
  abbrev: CIS
  email: adam.w.montville@gmail.com
  street: 31 Tech Valley Drive
  code: '12061'
  city: East Greenbush
  region: NY
  country: USA
- ins: P. Langlois
  name: Philippe Langlois
  org: Center for Internet Security
  abbrev: CIS
  email: philippe.langlois@cisecurity.org
  street: 31 Tech Valley Drive
  code: '12061'
  city: East Greenbush
  region: NY
  country: USA


normative:


informative:
  I-D.ietf-mile-xmpp-grid: xmppgrid
  CISControls:
    title: "CIS Controls"
  RFC7090:
  STIX:
    title: "STIX"
    target: https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=cti
  ATTACK:
    title: "ATT&K"
    target: https://attack.mitre.org/wiki/Main_Page



--- abstract

The MILE working group has adopted and continues work on {{-xmppgrid}} as a transfer protocol for security-relevant information between network-connected devices. SACM would like to make use of {{-xmppgrid}} as a transfer mechanism for security-relevant information beyond IODEF, and thus requires a taxonomy of semantically appropriate topics with contextually appropriate capabilities. This draft seeks to define this taxonomy.

WORKING GROUP: The source for this draft is maintained in GitHub.  Suggested changes should be submitted as pull requests at https://github.com/adammontville/ietf-mandl-sacm-tool-capability-language/.  Instructions are on that page as well.

--- middle


# Introduction

For the defenders supporting and protecting networks, the deluge of data, alerts, best practices, notices and regulations can overwhelm even the hardiest of us. Fortunately for the defenders the tools they use have evolved in maturity, functionality and interoperability. However, understanding the specific  capability of the tools and how they help you achieve certain regulations or best practices still presents a challenge. Does a vulnerability management platform also count as or contribute to an organization’s asset inventory? Does an Active Asset Inventory tool also help the enterprise create its list of active ports and services?  Does an organization's implementation of open source tools meet the same functional capabilities of a commercial tool (and vice versa)? What additional value does [insert new marketing buzzword] provide to protecting the organization?

One way to address these types of questions is through the development of a standardized language to describe security tooling capability. We have standardized languages for describing software weakness and vulnerability (CWE, CVE), standardized languages to describe platforms and software (CPE, SWID) and also some growing standardization for understanding attacker methodology and campaigns ({{RFC7090}}, {{STIX}}, {{ATTACK}}).  While the task of standardizing a language of tooling capabilities may seem insurmountable, we believe we can attach the problem by focusing on what the tools do rather than how they do it. With this approach we could start to whittle down the large corpus of tooling descriptions and distill them into a more manageable classes of capabilities.

By having a standardized approach to describing capabilities we could theoretically make direct connections between security tooling, security requirements and risks.

# Terms and Definitions

TBD

# What Not How

The key to this puzzle is to distinguish the what from the how, where the what is the action or activity that the tool is implementing/completing. For this exercise we referenced the {{CISControls}} as a good starting point to describe the specific capability that is required for the sub-control to be implemented. While going through the process a pattern was discovered, many of the sub-controls had a relatively consistent structure, with one of a handful of actions being applied to different subjects, listed as follows:

* Parse: read and interpret different files and data into an consistent format
* Scan: Examine parts of something to detect specific feature
* Store: Write values and data into a queryable format
* Block: Prevent a specific event from occurring
* Identify: Uniquely represent data points based on a specific premise or criteria
* Authenticate: Verify something’s identity based on a specific criteria
* Patch: To mend a weakness or vulnerability
* Rate: assign a standard or value to something according to a particular scale
* Verify: Demonstrate the accuracy of assumptions
* Log: make a recording of specific  events
* Set: Turn on a setting or add a value to the system
* Encrypt: convert plaintext information into ciphertext to prevent unauthorized access

Below is an example of how these action terms can be used:

* Scan the network for live assets,
* Scan assets for deviations to baseline,
* Scan assets for known malicious file hashes,
* Block from the network assets w/o legitimate certificates
* Block from executing unapproved applications
* Block from connecting unapproved connections.

In each of the above examples, there is an action and a subject. The subject allows us to understand where the action is being applied and within which context. For example are we scanning the network for live assets, or are we scanning for known out-dated software? The problem then becomes, what ultimately describes the subject - a subject could be an endpoint, an attribute on an endpoint, software installed on an endpoint, and so on.  Ideally a standardized language of system subjects would allow for the capturing of relationships between subjects (a Filesystem is on a system, a network consists of different systems, applications can be distributed across different systems).  The relationships would be key to understanding how specific capabilities tie back to different elements of the environment and how those protections roll up (or don’t) in the environment.

We can extend this to include one more piece of information: Scope. As much as we’d like to say that a capability could be applied universally across a given environment, the reality is that it may only be available to certain platforms. For example, a specific action may only be available on domain-joined systems in a Windows environment, or to systems with specific software installed. This scope would then help an operator understand the overall coverage of her organization’s security tools.   

Another way of looking at this is that a security tooling capability is a function of an action-subject-scope tuple, or :

Capabilities = f(Action, Subject, Scope)


#  IANA Considerations

TBD

#  Security Considerations

TBD

#  Acknowledgements

TBD

#  Change Log

TBD

# Contributors

--- back

# The Attic

TBD
