# Background on Basic Best Practices Criteria for Open Source Software (OSS)

This document gives background on the
Basic Best Practices Criteria for Open Source Software (OSS).
This includes potential sources of criteria,
identifying processes used by existing OSS project,
and capturing implementation notes for the tool that will
help projects determine (and demonstrate) that they meet these criteria.
See [criteria](./criteria.md) for the current version of the criteria.

There is no time or need to record *everything* that is related
in this document.
The goal of this document
is to identify enough material to reduce the risk that an important
relevant idea was overlooked.
The *primary* way we are avoiding that risk is through public
review and discussion of the criteria;
looking at other related information (documented here) is simply
a supplement.

In some cases this material is very rough.
We believed it was more important to capture background information,
even if it is rough,
and then clean it up over time if that cleanup is important.
Creating good criteria is our real objective, so please focus on the
[criteria](./criteria.md) list.

Please note that these are completely unrelated to the
[Construction Industry Institute (CII) best practices](https://www.construction-institute.org/Store/CII/Publication_Pages/bp.cfm?section=orders).

# Potential sources of criteria

This section basically provides a literature search of related materials.
These include
guidelines for OSS projects,
general methods for evaluating OSS projects,
security-related materials (e.g., guidelines or evaluation processes),
security-related metrics,
and miscellanea.
Some of these approaches may be useful for the badging system as well.

## Guidelines for OSS projects

Some guidelines include:

*   [Karl Fogel&#8217;s book *Producing Open Source Software*](<http://producingoss.com/)

*   [Civic Commons&#8217; wiki page](http://wiki.civiccommons.org/Open_Source_Development_Guidelines/)

*   [&#8220;Starting an Open Source project.&#8221;](http://www.smashingmagazine.com/2013/01/starting-an-open-source-project/)

*   [&#8220;Software Release Practice HOWTO.&#8221; Eric Raymond, 2000 (somewhat dated)](http://en.tldp.org/HOWTO/Software-Release-Practice-HOWTO/)

*   [&#8220;Releasing Free/Libre/Open Source Software (FLOSS) for Source Installation.&#8221; David A. Wheeler](http://www.dwheeler.com/essays/releasing-floss-software.html)


## Methods for evaluating OSS projects

There are a number of complete processes specifically for evaluating OSS
(as software, a project, or both). These typically evaluate OSS
for a particular purpose, not their security per se, but they may have
useful approaches that can be reused in criteria for a best practices badge.

### Callaway&#8217;s FAIL index

Tom &#8220;spot&#8221; Callaway, Fedora Engineering Manager at Red Hat, posted a
blog post titled &#8220;How to tell if a FLOSS project is doomed to FAIL (or
at least, held back...)&#8221; in 2009. The book *The Open Source Way*
includes a chapter with an updated version of this index and is
available online \[Callaway\]. This index is intended to be a quick
measure of how well a FLOSS project follows common practices,
particularly those that impede packaging or co-development by others. It
measures &#8220;FAIL&#8221; points, so *low* scores are better; 0 is perfect,
5 through 25 are &#8220;You&#8217;re probably doing okay, but you could be better,&#8221; and beyond 25
is an indicator of serious problems.

The measures are grouped into categories: size, source (version)
control, building from source, bundling, libraries, system install, code
oddities, communication, releases, history, licensing, and
documentation. Examples of causes for fail points are:

-   Source Control: There is no publicly available source control (e.g.,
    cvs, svn, bzr, git) \[ +10 points of FAIL \]

-   Building from source: There is no documentation on how to build from
    source \[ +20 points of FAIL \]

-   Communication: Your project does not have a mailing list \[ +10
    points of FAIL \], or your project does not have a website \[ +50
    points of FAIL\]

-   Licensing: Your code does not have per-file licensing \[ +10 points
    of FAIL \].

Obviously a high score does not always doom a project to fail, nor does
a low score guarantee success.
However, it can provide
a simple metric to point out potential issues in an OSS project.
It is intentionally designed to produce a numerical score, making it
relatively easy to report.

A updated discussion is here: <http://opensource.com/life/15/7/why-your-open-source-project-failing>.

### Internet Success

The book *Internet Success* by Schweik and English reports a detailed
quantitative analysis to answer the question,
&#8220;what factors lead some OSS commons
to success and others to abandonment?&#8221; \[Schweik2012\]

Schweik and English examined over 100,000 projects on SourceForge, using
data from SourceForge and developer surveys, and using quantitative analysis
instead of guesswork. They use a very simple project lifecycle model:
projects begin in initiation, and once the project has made its first
software release, it switches to growth. They also categorized projects
as success, abandonment, or indeterminate. Combining these produces six
categories of project: success initiation (SI); abandonment initiation
(AI); success growth (SG); abandonment growth (AG); indeterminant
initiation (II); and indeterminant growth (IG). Their operational
definition of success initiation (SI) is oversimplified but easy to
understand: an SI project has at least one release. Their operational
definition for a success growth (SG) project is very generous: at least
3 releases, at least 6 months between releases, and has more than 10
downloads.

One of the key results is that during initiation (before first release),
the following are the most important issues, in order of importance, for
success in an OSS project according to this quantitative data:

1.  &#8220;Put in the hours. Work hard toward creating your first release.&#8221;
    The details in chapter 11 tell the story: If the leader put in more
    than 1.5 hours per week (on average), the project was successful 73%
    of the time; if the leader did not, the project was abandoned 65% of
    the time. They are not saying that leaders should only put in 2
    hours a week; instead, the point is that the leader must
    consistently put in time for the project to get to its
    first release.

2.  &#8220;Practice leadership by administering your project well, and
    thinking through and articulating your vision as well as goals for
    the project. Demonstrate your leadership through hard work.&#8221;

3.  &#8220;Establish a high-quality Web site to showcase and promote your
    project.&#8221;

4.  &#8220;Create good documentation for your (potential) user and developer
    community.&#8221;

5.  &#8220;Advertise and market your project, and communicate your plans and
    goals with the hope of getting help from others.&#8221;

6.  &#8220;Realize that successful projects are found in both GPL-based and
    non-GPL-compatible situations.&#8221;

7.  &#8220;Consider, at the project&#8217;s outset, creating software that has the
    potential to be useful to a substantial number of users.&#8221;
    Remarkably, the minimum number of users is surprisingly small; they
    estimate that successful growth stage projects typically have at
    least 200 users. In general, the more potential users, the better.

Some items that people have claimed are important, such as keeping
complexity low, were not really supported as important. In fact,
successful projects tended to have a little more complexity. I suspect
both successful and abandoned projects often strive to reduce complexity,
so it not really something that distinguishes them.
Also, sometimes a project that focuses on user needs has to have more
complexity than one that does not, simply because user needs can
sometimes require some complexity.

Similarly, they had guidance for growth projects, in order of
importance, and these may suggest some metrics
(comments by David A. Wheeler are in parentheses):

1.  &#8220;Your goal should be to create a virtuous circle where others help
    to improve the software, thereby attracting more users and other
    developers, which in turn leads to more improvements in the
    software... Do this the same way it is done in initiation: spending
    time, maintain goals and plans, communicate the plans, and maintain
    a high-quality project web site.&#8221; The user community should be
    actively
    interacting with the development team.
> (Wheeler notes that possible related metrics include:
> actively maintained website (e.g., date of last page change on
> website), messages/month (e.g., email, bug tracker, etc.), number of
> commits/month, number of committers, etc.)

2.  &#8220;Advertize and market your project.&#8221; In particular, successful
    growth projects are frequently projects that have added at least one
    new developer in the growth stage.
> (Wheeler notes that possible related metrics include number of
> developers that have been added (post initial release or within a
> year).)

3. "Have some small tasks available for contributors with limited time."
> (Wheeler notes that a possible metric is a posted list of small tasks
> for new/limited contributors.)

4.  "Welcome competition." The authors were surprised, but noted that
    &#8220;competition seems to favor success.&#8221;
    Personally, I do not find this
    surprising at all. Competition often encourages others to do better;
    we have an entire economic system based on that premise.

5.  Consider accepting offers to finance or pay developers (they can
    greatly increase success rates). This one, in particular, should
    surprise no one; if you want to increase success, pay someone to do it.

6.  &#8220;Keep institutions (rules and project governance) as lean and
    informal as possible, but do not be afraid to move toward more
    formalization if it appears necessary.&#8221;

The book has more detailed lists of metrics.

They also have some hints for how potential OSS users (consumers) can
choose OSS that is more likely to endure. Successful OSS projects have
characteristics like more than 1000 downloads, users participating in
bug tracker and email lists, goals/plans listed, a development team that
responds quickly to questions, a good web site, good user documentation,
and good developer documentation. A larger development team is a good
sign, too.

### Stol and Babar

There are so many processes for evaluating OSS that Stol and Babar have
published a framework comparing them here:
<http://staff.lero.ie/stol/files/2011/12/OSS2010.pdf>. One complication
is that there are several methods named
&#8220;Open Source Maturity Model.&#8221;

### QualiPSo OpenSource Maturity Model (OMM)

The QualiPSo OpenSource Maturity Model (OMM) a methodology for assessing
Free/Libre Open Source Software (FLOSS) and more specifically the FLOSS
development process. This methodology was released in 2008 and is
released under the Creative Commons license.

A summary is at
<http://en.wikipedia.org/wiki/OpenSource_Maturity_Model>.

It defines three maturity levels: basic, intermediate, and advanced.

Basic level requirements:

-   PDOC - Product Documentation

-   STD - Use of Established and Widespread Standards

-   QTP - Quality of Test Plan

-   LCS - Licenses

-   ENV - Technical Environment

-   DFCT - Number of Commits and Bug Reports

-   MST - Maintainability and Stability

-   CM - Configuration Management

-   PP1 - Project Planning Part 1

-   REQM - Requirements Management

-   RDMP1 - Availability and Use of a (product) roadmap

Intermediate level requirements:

-   RDMP2 - Availability and Use of a (product) roadmap

-   STK - Relationship between Stakeholders

-   PP2 - Project Planning Part 2

-   PMC - Project Monitoring and Control

-   TST1 - Test Part 1

-   DSN1 - Design Part 1

-   PPQA - Process and Product Quality Assurance

Advanced level requirements:

-   PI - Product Integration

-   RSKM - Risk Management

-   TST2 - Test Part 2

-   DSN2 - Design 2

-   RASM - Results of third party assessment

-   REP - Reputation

-   CONT - Contribution to FLOSS Product from SW Companies

Unfortunately, we have had trouble accessing <http://www.qualipso.org/>
for more information.

### Wheeler OSS Evaluation model

David A. Wheeler (the author) has previously described a general process
for evaluating open source software in &#8220;How to Evaluate Open Source
Software / Free Software (OSS/FS) Programs.&#8221; \[Wheeler2011e\].

This process is based on four steps: Identify candidates, Read existing
reviews, Compare the leading programs&#8217; basic attributes to your needs,
and then Analyze the top candidates in more depth. This set of Identify,
Read Reviews, Compare, and Analyze can be abbreviated as &#8220;IRCA&#8221;.
Important attributes to consider include functionality, cost, market
share, support, maintenance, reliability, performance, scaleability,
useability, security, flexibility/customizability, interoperability, and
legal/license issues.

Its section on security mentions some metrics that might be useful:

-   Coverity scan results, including the rung achieved, number of
    defects, and defect density.

-   Fortify scan results (similar)

-   Common criteria evaluation. These typically evaluate entire systems
    (e.g., entire operating systems) instead of focusing on specific
    projects that support a particular portion of an operating system.
    Thus they do not provide the kinds of measures desired for this task.

-   Reports of (many) vulnerabilities that are
    &#8220;unforgiveable&#8221; (MITRE
    identifies criteria for identifying vulnerabilities that are
    especially easy to find, and thus are
    &#8220;unforgiveable&#8221;) \[Christey2007\].

-   It is *known* that external organizations have or are reviewing the
    software, e.g., OpenBSD. However, some organizations (like OpenBSD)
    fix only *their* version, which may not be the version all
    other systems use.

It also notes that experts can be hired to determine whether the developers
follow good security practices. Examples include:

-   It minimizes privileges (e.g., only small portions of the program
    have special privilege, or the program only has special privileges
    at certain times).

-   It strives for simplicity (simpler designs are often more secure).

-   It carefully checks inputs.

-   Source code scanning tools such as RATS and Flawfinder report
    few problems.

Its section on reliability notes metrics that may be useful are:

-   Self-reported status (e.g., &#8220;mature&#8221;)

-   Presence of an automated (regression) test suite.

### Gratis-Security

In 2003 David A. Wheeler developed an unpublished list of techniques
that might be useful in an inexpensive evaluation approach he called
&#8220;gratis security.&#8221;
This was intended to be a process for self-evaluation
that could be performed with zero or little cost by developers.
It also tried to connect, in some cases, with the Common Criteria
as it existed at the time.
It had several different levels, with higher levels requiring more.

The following might be relevant.

Use Automated Tools:

1.  Use source code security scanning packages, such as flawfinder and RATS. E.G., for level 1, the software must not have top risk warnings from RATS and flawfinder (inserting comments to disable them is fine as long as the person asserts that they checked the warnings to ensure that they weren&#8217;t really problems). For level 3, the software must not have warnings from the top 2 risk levels.

2.  Use execution testing tools, such as Brute Force Binary Tester and Whisker (for web-accessible programs) to send data in an attempt to break the program.

3.  Use tools to detect common software engineering flaws that are sometimes exploitable, e.g., valgrind.

4.  Use other automated tools, such as port scanners (e.g., Nessus), network sniffers, and file scanning tools to identify cleartext that should not be cleartext.

5.  Specialized tools could be used to search for specific security flaws (buffer overflows, temporary file use, etc.).

6.  Note that new tools could be developed as part of this evaluation scheme, and/or scripts to automate the entire process.

7.  See Fyodor&#8217;s security tool list for additional ideas.

Require active peer review:

1.  Evidence of multiple developers (e.g., in a ChangeLog). E.G., for level 2, the project must have at least 2 developers.

2.  Evidence of people reviewing code (e.g., bug reports/patches).

3.  Public disclosure of source code, for some time.

4.  (For level 5): Evidence that all code has been reviewed by someone else.

5.  Evidence that there are a number of users (e.g., for level 4, at least 100 users).

6.  Require that at least some developers learn how to write secure programs, including what to look for. There are freely available materials, such as <http://www.dwheeler.com/secure-programs> that teach how to do this. E.g., at level 2, at least 2 developers (including one trusted developer) has asserted that they&#8217;ve read at least one book on how to write secure programs. Level 5: all trusted developers have read at least one book.

Good Practices:

1.  Products must have a different version number for each public release (CC ACM\_CAP.1).

2.  Level 1: Products (source and binary) must be signed, the public key must be publicly posted (so it can be verified over time) and have an MD5 posted. This provides a simple way to check the product signature (keep signature from a while back - that way, if the website is broken, others can tell there&#8217;s a change).

3.  Trusted repository configured so that only trusted developers can change code, and passwords not sent in clear (at least, must be setup so don&#8217;t need to & developers know not to do so).

4.  Upper level: require CM system so can see what each developer changed and when. CVS and subversion are fine. (see CC ACM).

5.  Installation procedures discuss how to install securely & security issues (like CC ADO\_IGS.1, AGD\_ADM.1, AGD\_USR.1)

6.  Upper levels: Start to connect with the CC. e.g., creating an ST to at least document the threats and security requirements.

The &#8220;good practices&#8221; list probably needs to be divided further.
Where possible, it might be possible to base the grouping on the CC:
Configuration Management, Delivery and Operation, Development, Guidance
Documents, Life cycle support, Tests, Vulnerability Assessment. Here&#8217;s
an alternative grouping, based on the TSDM: Configuration management
(CM), identification & authentication (I&A), auditing, access control,
development environment administration, trusted distribution,
documentation (document what the product should and should not do - see
the CC for more details about this), personnel (are they all identified?
At higher levels, citizenship issues?).

### Talk Openly Develop Openly (TODO)

Talk Openly Develop Openly (TODO)
is "an open group of companies who want to collaborate on practices, tools, and other ways to run successful and effective open source projects and programs."
Their "about" page states that " We will be sharing experiences, developing best practices, and working on common tooling."
At this time they have not publicly released a best practices list.

More information: <http://todogroup.org>


## Security-related

### OWASP Application Security Verification Standard (ASVS)

The OWASP Application Security Verification Standard (ASVS) Project
provides &#8220;a basis for testing web application technical security
controls.&#8221; In particular, the publish the OWASP Application Security
Verification Standard (ASVS); all is available here:

<https://www.owasp.org/index.php/Category:OWASP_Application_Security_Verification_Standard_Project>

The following comments are about the 2014 edition (the version available
at the time of this writing). This document is focused *solely* on web
applications; it has much useful information for that case, but it&#8217;s not
obvious how to apply this document to many other kinds of programs.

The 2014 edition has some major changes from the 2009 version. In
particular, it focuses on the goal (what to be accomplished) and not the
how. This meant that while the 2009 version discussed specific
approaches (dynamic scanning, static analysis, Threat Modeling, and
design reviews), the 2014 version does not. Instead, the 2014 version
defines &#8220;security requirements that must be verified for an application
to achieve a certain level. How those requirements are verified is left
up to the verifier.&#8221;

### OWASP OpenSAMM

OpenSAMM is documented here: <http://www.opensamm.org/>

### SANS&#8217; Securing Web Application Technologies (SWAT)

SANS has released the &#8220;Security Web Application Technologies&#8221; (SWAT)
checklist, available at:
<https://software-security.sans.org/resources/swat>.

This checklist is grouped into the following categories:

-   Error Handling and Logging

-   Data Protection

-   Configuration and operations

-   Authentication

-   Session Management

-   Input and Output Handling

-   Access Control

Many of these require human responses, and are not easy to (completely)
automate. As the name implies, this is focused on web applications. The
checklist items are cross-referenced to the relevant CWE entries - a
nice touch.

### Build Security In

The US DHS "Build Security In" website
"provides practices, tools, guidelines, rules, principles, and
other resources that software developers, architects, and security
practitioners can use to build security into software in every phase of
its development."
See <https://buildsecurityin.us-cert.gov/>.

### OWASP CLASP

CLASP (Comprehensive, Lightweight Application Security Process)
"provides a well-organized and structured approach for moving security
concerns into the early stages of the software development lifecycle,
whenever possible.  CLASP is actually a set of process pieces that can
be integrated into any software development process."

See: <https://www.owasp.org/index.php/Category:OWASP_CLASP_Project>.


### BSIMM

Building Security In Maturity Model (BSIMM)
provides information about organizational software security initiatives,
and lets people compare their initiatives with others'.
https://www.bsimm.com/

### Heartbleed Lessons Learned

The Heartbleed vulnerability in OpenSSL could not be found by many of
the techniques used to counter vulnerabilities. However, a number of
techniques *could* have found Heartbleed ahead-of-time. OSS projects
that have significant security concerns should determine if they could
have similar vulnerabilities, and if so, should include at least one
technique that could counter it. A list of techniques that could have
countered Heartbleed is given in \[Wheeler2014h\].

## Common Criteria

The Common Criteria for Information Technology Security Evaluation (abbreviated as Common Criteria or CC) is an international standard (ISO/IEC 15408) for computer security certification.

Common Criteria is a framework where security functional and assurance requirements (SFRs and SARs respectively) can be specified in Protection Profiles (PPs).  Suppliers can then claim what requirements they meet in a Security Target (which could cover 0 or more Protection Profile requirements).  Typically testing labs evaluate products to determine if they meet the claims.

The Common Criteria typically focuses on the use of independent labs,
who spend time evaluating a large set of documentatary evidence.
That is radically different than the approach taken here.

## SAFECode

The Software Assurance Forum for Excellence in Code (SAFECode)
organization at
<http://www.safecode.org/>
has a variety of materials.
They have a variety of training materials that developers might find useful.
Some of their publications might include points that could
strengthen the criteria.
SAFECode publications are available at:
<http://www.safecode.org/publications/>.


## Specific potentially useful security metrics

Many metrics have been proposed for evaluating software that are more
security-focused. Some are focused on security.

### In-depth static analysis security tools (e.g., Coverity Scan)

Some tools are specifically designed to look for potential security
vulnerabilities and report them. Their sheer counts, perhaps limited to
most severe and/or computed as densities, might give an indication of
the security (or lack thereof) of software.

Coverity sells a proprietary tool that looks for security
vulnerabilities. Coverity Scan, at <https://scan.coverity.com/>, is &#8220;a
service by which Coverity provides the results of analysis on open
source coding projects to open source code developers that have
registered their products with Coverity Scan.&#8221; It supports C, C++, Java,
and C\#. An OSS project developer must specifically register their
project to participate; results are then sent to the project developers.

The Coverity Scan project was initially launched under a contract with
the Department of Homeland Security (DHS) to harden open source software
which provides critical infrastructure for the Internet. Coverity Scan
began in collaboration with Stanford University on March 6, 2006. During
the first year of operation, over 6,000 software defects were fixed
across 50 C and C++ projects by open source developers using the
analysis results from the Coverity Scan service. DHS support ended in
2009, but the service has continued.

A list of projects covered by Coverity scan is at
<https://scan.coverity.com/projects>; over 3200 participate. Even though
the exact results are not posted publicly, the fact that *a project is
on the list* maintained by Coverity is public, and that may by itself
indicate that a project is interested in detecting and fixing
vulnerabilities. A few projects have achieved &#8220;rung 2&#8221; which is a higher
achievement.

A similar argument could apply to other tool makers who make tools that
perform in-depth static analysis of software and provide scans of OSS
projects. For example, HP/Fortify will provide static analysis tools for
use in examining open source software, in partnership with Sonatype;
details are here: <https://www.hpfod.com/open-source-review-project>.

There are some OSS tools that look for vulnerabilities, e.g., splint
(for C only), that might perform such a role. (Note, however, that
splint has not been maintained recently.)

Note that these tools use heuristics to determine what is a
vulnerability, thus, different tools will report different values.

### Lexically scanning static analysis security tools (e.g., flawfinder and RATS)

A variant is to use lexically scanning tools to report constructs
(&#8220;hits&#8221;) in software that are of special concern. Again, counts or
densities could be reported. OSS tools such as flawfinder and RATS can
do this. (Note: David A. Wheeler is the author of flawfinder.)

IDA has previously done in-house work measuring hit density, where hits
are reports from flawfinder or another lexical tool, and the density is
found by dividing by physical source lines of code. These tools simply
report riskier constructs, not really vulnerabilities, but the theory is
that if developers often use riskier constructs, they are more likely to
produce insecure results. A comparison of sendmail and postfix of years
ago suggests this might be a useful measure.

### Metrics from Wikipedia article on OSS Security

Wikipedia&#8217;s article on &#8220;Open-Source Software security&#8221; has various
comments about OSS security, including references to metrics and models.
The following is from the page
<http://en.wikipedia.org/w/index.php?title=Open-source_software_security&oldid=627231105>
(which is a permanent link).

Metrics they mention include:

-   Number of days between vulnerabilities. &#8220;It is argued that a system
    is most vulnerable after a potential vulnerability is discovered,
    but before a patch is created. By measuring the number of days
    between the vulnerability \[being found\] and when the vulnerability
    is fixed, a basis can be determined on the security of the system.
    There are a few caveats to such an approach: not every vulnerability
    is equally bad, and fixing a lot of bugs quickly might not be better
    than only finding a few and taking a little bit longer to fix them,
    taking into account the operating system, or the effectiveness of
    the fix.&#8221;

-   Morningstar model. &#8220;By comparing a large variety of open source and
    closed source projects a star system could be used to analyze the
    security of the project similar to how Morningstar, Inc. rates
    mutual funds. With a large enough data set, statistics could be used
    to measure the overall effectiveness of one group over the other. An
    example of such as system is as follows:\[7\]

    -   1 Star: Many security vulnerabilities.

    -   2 Stars: Reliability issues.

    -   3 Stars: Follows best security practices.

    -   4 Stars: Documented secure development process.

    -   5 Stars: Passed independent security review.&#8221;

-   Coverity (see discussion on Coverity)

### Origin analysis for known vulnerabilities

Today software is often composed from other systems, transitively.
Unfortunately, these transcluded components may have known
vulnerabilities.

Various tools, both OSS and proprietary, can examine software to see if
it includes components that have known vulnerabilities. Such tools
include OWASP Dependency-check, as well as tools from Sonatype, Black
Duck, and Codenomicon.

## Miscellaneous

### Madrid 2015 meeting

The Core Infrastructure Initiative (CII) 2015 meeting in Madrid, Spain,
discussed best practices.
Issues raised included the following:


*   There is a need for a community of practice to develop and iterate its own definition of “best”
*   Bring in cognitive/behavioral scientists to discuss the implementation of incentive models that can raise the state of the ecosystem and avoiding incentives that produce perverse outcomes. (This is not to *trick* people, but to increase the chance of it working.)
*   Match resources with best practice requirements (so projects won't have the problem of being unable to meet the standard due to under-resourcing).

### Checklist Manifesto

The *Checklist Manifesto* by Dr. Atul Gawande is not a specific set of
criteria for software, but instead is general non-fiction book
advocating the use of checklists and emphasizing how to make effective
checklists.

The &#8220;badges&#8221; contemplated here do not need to be simple checklists; it
may be fine to have a more thorough list, or if some requirements take
time to do. Nevertheless, the checklist manifesto is noted here because
it clearly shows that simple &#8220;to do&#8221; lists, if carefully written, can
have dramatically positive effects.


# Practices of some existing OSS Projects

This section describes the practices of some existing OSS projects,
particularly a few that are popular, apply practices we might want
to consider adding to the best practices, and/or reputed by someone
to be well-run.
Examining some existing OSS projects
can help us identify important practical activities.
Indeed, if many well-run projects do *not* perform a
specific practice, it may not be a good practice.
We believe that well-run OSS projects
shouldn&#8217;t need to make many
changes to meet the basic best practices.

Many OSS projects *do* a number of things well.
Indeed, we intend for there to be many &#8220;0-day badge recipients&#8221; -
that is, OSS projects that are already meet the criteria.
Of course, projects that follow best practices can still
have vulnerabilities, other bugs, and other kinds of problems...
but they should be a better position to prevent, detect, and fix them.

We hope to survey a number of OSS projects.
Below is a summary of some information about the
Linux kernel, OpenBSD, OpenSSH, LibreOffice, SQLite,
the Global Positioning System Service Daemon (GPSD), and Postfix.
Some other OSS projects that might be surveyed include
the Apache web server, Firefox, Chromium, MySQL or MariaDB, git,
Bouncy Castle, SAMBA, Spamassassin, Smoothwall, KeePass, VLC,
pidgin, dovecot, gcc, busybox, node.js, and jquery.

Here are some pages describing the processes used by some OSS projects
to produce high-quality and/or high-security software.
Some of this material is derived from
[*How to Prevent the next Heartbleed*](http://www.dwheeler.com/essays/heartbleed.html#exemplars).
Note that any substantive project is difficult to summarize;
the text below is necessarily a broad brush.

## Linux kernel

The Linux kernel is an operating system kernel.
Its primary project page is <https://www.kernel.org/>.

Some pages that describe the Linux kernel development process include:
[Linux kernel documentation on its development](https://www.kernel.org/doc/Documentation/development-process/),
especially
[its file on the development process](https://www.kernel.org/doc/Documentation/development-process/2.Process),
the
[Linux Foundation page on how its development process works](http://www.linuxfoundation.org/content/2-how-development-process-works),
["The changing kernel development process" presentation by Jon Corbet (LWN.NET) given in 2014](https://www.youtube.com/watch?v=GQiik7X7-u8), and
["Greg Kroah Hartman on the Linux Kernel" (2008)](https://www.youtube.com/watch?feature=player_detailpage&v=L2SED6sewRw#t=867s)
More generally, <http://lwn.net> reports on
Linux kernel development processes and results.

The Linux kernel is released under the
GPL version 2 (only) license.
Its license is clearly stated in its top-level COPYING file
(this file contains more than just the GPLv2 license).

The Linux kernel developers emphasize human code review and trust in
a smaller group of developers who are extremely experienced with Linux.
Once patches are posted, working with reviewers is a crucial part
of the development process.
There is strong continuity; many of its developers are the same people
who have lengthy experience with the software.
Most Linux kernel developers are paid to develop it, and
most contributions are from people paid to develop it;
both percentages have increased over time.

Currently Linux kernel releases occur every 2-3 months.
This makes it easy to refuse adding a new feature before it
is ready, because if it not clearly ready, it can be simply
deferred to the next release.
The Linux kernel's development process documentation explains,
"at the beginning of each development
cycle, the 'merge window' is said to be open.  At that time, code which is
deemed to be sufficiently stable (and which is accepted by the development
community) is merged into the mainline kernel.  The bulk of changes for a
new development cycle (and all of the major changes) will be merged during
this time, at a rate approaching 1,000 changes ("patches," or "changesets")
per day.
(As an aside, it is worth noting that the changes integrated during the
merge window do not come out of thin air; they have been collected, tested,
and staged ahead of time...)...
The merge window lasts for approximately two weeks.  At the end of this
time, Linus Torvalds will declare that the window is closed and release the
first of the "rc" kernels...
[and] the time to stabilize the next kernel has begun.
Over the next six to ten weeks, only patches which fix problems should be
submitted to the mainline.  On occasion a more significant change will be
allowed, but such occasions are rare..."
Patches generally go through early review and a wider review;
if they pass muster, it will be accepted by the subsystem maintainer,
and (hopefully) will eventually be merged into the mainline
repository managed by Linus Torvalds.

The Linux kernel development is managed as a distributed
development process.
Most developers use the tool git (git was originally
developed to support Linux kernel development).
Group communication primarily takes place via mailing lists.
Most subsystems have a designated maintainer, who is the gatekeeper
for that portion of the kernel.

The Linux kernel developers intentionally do not use an issue tracker
(there is one, but it is not generally used); many
key developers do not believe
that issue trackers are helpful for the very large scale of their project.

The Linux kernel has a standard coding style (though not all of the
code meets it).
The guidelines for code submission recommend that new code
not produce any compiler warnings and that the full set of warnings
be enabled (they are not enabled by default).
The "checkpatch.pl" program is a simple perl program
that does a simple static analysis of proposed patches for
common problems.
The Linux kernel provides several (runtime) debugging features,
such as "lockdep" for tracking lock acquisition and release.

In 2014 a new make target called "kselftest" was added to the
kernel build system
(see <https://lwn.net/Articles/608959/> for more).
The xfstests suite also performs tests and is actively maintained at
http://oss.sgi.com/cgi-bin/gitweb.cgi?p=xfs/cmds/xfstests.git;a=summary
There are automated test processes, including the
[Linux test project](http://linux-test-project.github.io/)
and
[Autotest](http://autotest.github.io/)
https://lwn.net/Articles/654071/
In 2015 the libnvdimm subsystem was added to the kernel's
driver infrastructure (it provides services over persistent memory
to make access to that memory safer and more reliable);
it appears to be the first device-driver subsystem to integrate
in-kernel interface mocking techniques in support of unit testing,
as further discussed in
https://lwn.net/Articles/654071/ .
Many major GNU/Linux distributions also include some additional
certification systems to check a Linux kernel.
That said, [Greg Kroah-Hartman](https://www.youtube.com/watch?feature=player_detailpage&v=L2SED6sewRw#t=867s) notes that it is very difficult
to create true test suites for a kernel, so the Linux kernel
strongly depends on community testing.

A variety of static analysis tools are used to analyze the Linux kernel.
The "sparse" static analysis tool was initially developed by
Linus Torvalds and can be used to find certain kernel code problems.
The "Coccinelle" tool (http://coccinelle.lip6.fr/) can also find
many problems and sometimes propose fixes.
[Eduard Bachmakov worked on the clang static analyzer in 2013 to improve its ability to detect Linux kernel defects](http://www.linux.com/news/featured-blogs/200-libby-clark/749649-a-summer-spent-on-the-llvm-clang-static-analyzer-for-the-linux-kernel).
["Linux Kernel Developer Responses to Static Analysis Bug Reports" by Philip J. Guo and Dawson Engler](https://www.usenix.org/legacy/event/usenix09/tech/full_papers/guo/guo_html/)
examined "how Linux kernel developers respond to bug reports issued by a static analysis tool" (in particular how they triaged reports),
using Coverity Scan results.

The Linux kernel has been fuzzed using the Trinity fuzz tester.
The future of the Trinity fuzzer is in doubt, however; see
https://lwn.net/Articles/650824/ .
There is also a specialized fuzzer for fuzzing perf_events
https://lwn.net/Articles/653182/ .

Note that running static analysis and fuzzing tools is typically not
required of initial contributors.
Instead, they are typically applied
by others who then report on any issues they find.

## OpenBSD

OpenBSD is an operating system (including a kernel).
Its main web page is <http://www.openbsd.org>.
They aspire to be #1 in security.

The [OpenBSD security page](http://www.openbsd.org/security.html)
describes the general development approach for OpenBSD
(this is also the approach taken by OpenSSH).

Their primary approach is comprehensive file-by-file analysis,
"not so much looking for security holes,
as we are looking for basic software bugs...
Entire new classes of security problems have been found during our audit,
and often source code which had been audited earlier
needs re-auditing with these new flaws in mind.
Code often gets audited multiple times,
and by multiple people with different auditing skills...
During our ongoing auditing process we find many bugs,
and endeavor to fix them even though exploitability is not proven."

They use a variety of ways to help solve problems, for example:

*   strlcpy() and strlcat() (these help counter buffer overflows)
*   Memory protection purify
*   Privilege separation
*   Privilege revocation
*   Chroot jailing


## OpenSSH

OpenSSH implements SSH connectivity tools (e.g., ssh and scp)
for encrypted connections.
Its primary website is <http://www.openssh.com/>.

The [OpenBSD security page](http://www.openbsd.org/security.html)
describes the general development approach for OpenBSD;
this is also the development approach taken by OpenSSH.

One unusual aspect is that they
[split their core development efforts from portability developments](http://www.openssh.com/history.html#portable).
One team does strictly OpenBSD-based development (to be as simple as possible),
and the other team takes that version and makes it portable
to run on many operating systems.

Its top-level LICENSE file contains licensing information;
this is complex in detail.
The file notes that "we will summarize and say that all components
are under a BSD licence, or a licence more free than that."

The OpenSSH developers have worked to
reduce OpenSSH&#8217;s attack surface; their approaches include
defensive programming (preventing errors by
inserting additional checks),
avoiding complexity in dependent libraries,
mildly changing the protocol to reduce attack surface,
privilege separation,
and changing the program to maximize the benefit
of attack mitigation measures in the operating system (OS)
[<a href="http://www.openbsd.org/papers/openssh-measures-asiabsdcon2007.pdf">Miller2007</a>].
For more on how OpenSSH implements privilege separation, see
[<a href="https://www.usenix.org/events/sec03/tech/full_papers/provos_et_al/provos_et_al.pdf">Provos2003</a>].

## LibreOffice

LibreOffice 5.0 uses variety of tools to detect defects to fix.
These include
cppcheck,
building without any compile warnings using various warning
flags (e.g., -Werror -Wall -Wextra),
Coverity (working to zero Coverity bugs),
PVS-Studio messages,
paranoid assertions, fuzzing,
clang plugins/checkers,
increasing unit testing (their ideal is that every bug fixed gets a
unit test to stop it from recurring),
Jenkins / CI integration with gerrit to test across 3 platforms,
and coding guidelines.
https://people.gnome.org/~michael/blog/2015-08-05-under-the-hood-5-0.html

The primary LibreOffice license is the Mozilla Public License version 2.0
(MPL-2.0), and they ask that all contributions
be dual-licensed under the MPL-2.0 and the Lesser GPL (LGPL) version 3+.
This is explained in its
[Licenses page](https://www.libreoffice.org/about-us/licenses/),
including a link to individual developer statements.
The top-level files of libreoffice/core
contain the files COPYING (contains GPLv3), COPYING.LGPL
(contains LGPLv3),
and COPYING.MPL (contains the Mozilla Public License Version 2.0),
but it might not be obvious where each license applies just from
those files.


## SQLite

The SQLite developers emphasize extremely thorough (dynamic) testing.
As of version 3.8.10, the SQLite library consists of approximately 94.2
KSLOC of C code. (lines of code excluding blank lines and comments).
"By comparison, the project has 971 times as much test code and test
scripts - 91515.5 KSLOC."

Their approach to testing can be summarized as follows (per their website):

*   Three independently developed test harnesses
*   100% branch test coverage in an as-deployed configuration
*   Millions and millions of test cases
*   Out-of-memory tests
*   I/O error tests
*   Crash and power loss tests
*   Fuzz tests
*   Boundary value tests
*   Disabled optimization tests
*   Regression tests
*   Malformed database tests
*   Extensive use of assert() and run-time checks
*   Valgrind analysis
*   Undefined behavior checks
*   Checklists

Here are a few interesting quotes:

*   "Whenever a bug is reported against SQLite, that bug is not considered fixed until new test cases that would exhibit the bug have been added to either the TCL or TH3 test suites."
*   "Another popular [coverage] metric is 'Modified Condition/Decision Coverage' or MC/DC...  [SQLite] achieves 100% MC/DC in addition to 100% branch coverage."
*   "The developers of SQLite have found that full coverage testing is an extremely effective method for locating and preventing bugs. Because every single branch instruction in SQLite core code is covered by test cases, the developers can be confident that changes made in one part of the code do not have unintended consequences in other parts of the code. The many new features and performance improvements that have been added to SQLite in recent years would not have been possible without the availability full-coverage testing.  Maintaining 100% MC/DC is laborious and time-consuming. The level of effort needed to maintain full-coverage testing is probably not cost effective for a typical application. However, we think that full-coverage testing is justified for a very widely deployed infrastructure library like SQLite, and especially for a database library which by its very nature 'remembers' past mistakes."
*   "To help ensure that SQLite does not make use of undefined or implementation defined behavior, the test suites are rerun using instrumented builds that try to detect undefined behavior. For example, test suites are run using the "-ftrapv" option of GCC. And they are run again using the "-fsanitize=undefined" option on Clang. And again using the "/RTC1" option in MSVC. Then the test suites are rerun using options like "-funsigned-char" and "-fsigned-char" to make sure that implementation differences do not matter either. Tests are then repeated on 32-bit and 64-bit systems and on big-endian and little-endian systems, using a variety of CPU architectures. Furthermore, the test suites are augmented with many test cases that are deliberately designed to provoke undefined behavior. For example: "SELECT -1*(-9223372036854775808);".
*   "The SQLite core contains 4197 assert() statements that verify function preconditions and postconditions and loop invariants."
*   "SQLite compiles without warnings on GCC and Clang using the -Wall and -Wextra flags on Linux and Mac and on MSVC on Windows. No valid warnings are generated by the Clang Static Analyzer tool 'scan-build' either (though recent versions of clang seem to generate many false-positives.)...  Static analysis has not proven to be especially helpful in finding bugs in SQLite. Static analysis has found a few bugs in SQLite, but those are the exceptions."

For more information on how SQLite is tested, see: <https://www.sqlite.org/testing.html>.

All of the code and documentation in SQLite has been dedicated
to the public domain, as
[stated on its website](https://www.sqlite.org/copyright.html).
One of the three test harnesses, the TH3 test harness,
is a set of proprietary tests (this is the suite that gives 100%
branch coverage and 100% MC/DC test coverage).
There is no COPYING or LICENSE file at the top level of the source
distribution, and its README.md file does not clearly state the license.

## Global Positioning System Service Daemon (GPSD)

Global Positioning System Service Daemon (GPSD) is a daemon
that monitors one or more GPSes or AIS receivers attached
to a host computer and makes all data on the
location/course/velocity of the sensors available
to be queried on TCP port 2947 of the host computer.
It is widely used, e.g.,
it underlies the map service on Android phones, and is in many other
devices that need location information (e.g., drones).
Its main website is <http://www.catb.org/gpsd>.

It is released under the BSD-new license, aka Revised BSD or 3-clause license.

GPSD uses git and has a public repository, visible at:
http://git.savannah.gnu.org/cgit/gpsd.git

The GPSD project uses
<a href="http://www.aosabook.org/en/gpsd.html">extensive regression testing,
rigorous static checking with multiple tools
and an architectural approach that reduces risks
(e.g., they forbid the use of malloc in the core)</a>.
They use a custom framework for an extensive regression testing suite,
including the use of tools like valgrind.
Their static analysis tools include splint, cppcheck, and Coverity.
Its lead developer reports that,
&#8220;we do not know of any program suite larger than GPSD that
is fully splint-annotated, and strongly suspect that none such yet exist...
GPSD is notable as the basis for my assertion that conventional good
practice with C can get you very close to never-break. I got fanatical
about regression testing and routinely applying four static analyzers;
it paid off.&#8221;
The [lead developer has provided other comments about GPSD development processes](http://esr.ibiblio.org/?p=4340).

## Postfix

Postfix is a mail server.
Its primary website is <http://www.postfix.org>.
Elaine R. Palmer and Bill Cheswick have reported that htey
thought that Postfix did an overall
good job on security and reliability.

The
<a href="http://www.360is.com/06-postfix.htm">Postfix approach
for developing secure software</a>
emphasizes using
a very experienced team of just a few security conscious individuals,
writing it from scratch to be secure (and in particular resistant to
buffer overflows), and an architecture that involves
running as a set of daemons each performing a different set of tasks
(facilitating a &#8220;least privilege&#8221; approach
that can be easily contained further using chroot or virtual containers).
Postfix is implemented using a safe subset of C and POSIX, combined with an
<a href="https://en.wikipedia.org/wiki/Postfix_%28software%29#Implementation">abstraction layer that creates safe alternatives</a>.
For example, it has a &#8220;vstring&#8221; primitive to help resist
buffer overflow attacks and a
&#8220;safe open&#8221; primitive to resist race conditions.

It is released under the
<a href="http://mirrors-usa.go-parts.com/postfix/source/index.html">IBM Public License</a>.

Source is released as a .tar.gz tarball.
No official public version control repository has been identified.


# Implementation

We intend to implement a simple web application
to quickly capture self-assertion data, evaluate what it can automatically,
and provide badge information.
That application will itself be OSS, of course, and
we intend for the application to meet its own criteria.
We&#8217;ll probably implement it using Ruby on Rails
(since Rails is good for very simple web applications like this one).
We&#8217;re currently thinking of using Rails version 4.2,
storing the data in Postgres or MySQL/MariaDB, and using
RSpec, Cucumber, and FactoryGirl.
Our emphasis will be on keeping the program *simple*.

How handle authentication?
For GitHub projects, can hook into GitHub OAuth... if they can administer
a GitHub project, then they can report on that project.
Probably use &#8220;divise&#8221; module for authentication in Rails, that
works with GitHub.

We intend to make the *username* public of who entered data for each project
(generally that would be the GitHub username).
Also have our own login system, and support that, for those who don&#8217;t
want to use GitHub.

Once someone enters data on a project, normally only that person
(or a co-administator on GitHub) can edit the data of that project.
The Linux Foundation can override.
In the longer term we'll need to support transition, but that is
relatively uncommon so there's no need for it initially.

Naming is a challenge. The *real* name, for our purposes, is the
project URL.
Multiple projects may have the same human-readable name.


## GitHub-related badges

Pages related to GitHub-related badges include:
http://shields.io/
https://github.com/badges/shields
http://nicbell.net/blog/github-flair

We want GitHub users to think of this
as &#8220;just another badge to get&#8221;.

We intend to sign up for a few badges to evalute their onboarding process,
e.g., Travis (CI automation), Code Climate (code quality checker including
BrakeMan), Coveralls (code coverage), Hound (code style),
Gymnasium (checks dependencies), HCI (looks at your documentation).
For example, they provide the markdown necessary to embed the badge.
See ActiveAdmin for an example, take a few screenshots.
Many of these badges try to represent real-time status.
We might not include these badges in our system, but they
provide useful examples.

## License detection

Some information on how to detect licenses can be found in
&#8220;Open Source Licensing by the Numbers&#8221; (Ben Balter)
https://speakerdeck.com/benbalter/open-source-licensing-by-the-numbers


# Bibliography

Not all of these items are referenced directly, but they may still
be useful.

\[Callaway\] Callaway, Tom. &#8220;How to tell if a FLOSS project is doomed to
FAIL.&#8221; *The Open Source Way*.
<https://www.theopensourceway.org/wiki/How_to_tell_if_a_FLOSS_project_is_doomed_to_FAIL>

\[Christey2007\] Christey, Steve. Unforgiveable Vulnerabilities.
2007-08-02. <http://cve.mitre.org/docs/docs-2007/unforgivable.pdf>

\[Crowston2003\] Crowston, K., H. Annabi, and J. Howison. &#8220;Defining open
source software project success.&#8221; *ICIS 2003: Proceedings of the 24^th^
Internatinoal Conference on Information Systems* (Seattle, WA). 2003.

\[Fenton1997\] Fenton, N.E. and S.L. Pfleeger. Software metrics: a
Rigorous & Practical Approach. International Thompson Press. 1997.

\[Ghapanchi2011\] Ghapanchi, Amir Hossein , Aybuke Aurum, and Graham
Low. &#8220;A taxonomy for measuring the success of open source software
projects.&#8221; *First Monday*. 2011.
<http://firstmonday.org/ojs/index.php/fm/article/view/3558/3033>

\[Halstead1977\] Halstead, M.H. Elements of Software Science. Elsevier.
1977.

\[Hofman2009\] Hofmann, Philipp and Dirk Riehle. &#8220;Estimating Commit
Sizes Efficiently.&#8221;
<http://dirkriehle.com/wp-content/uploads/2009/02/hofmann-riehle-oss-2009-final.pdf>

\[Howard2003\] Michael Howard, Jon Pincus, and Jeannette M. Wing.
Measuring Relative Attack Surfaces. 2003.
http://www.cs.cmu.edu/\~wing/publications/Howard-Wing03.pdf

\[Manadhata2004\] Manadhata, Pratyusa, and Jeannette M. Wing. &#8220;Measuring
a System&#8217;s Attack Surface&#8221;. January 2004. CMU-CS-04-102.
<http://www.cs.cmu.edu/~wing/publications/tr04-102.pdf>

\[Manadhata2007\] Manadhata, Pratyusa K., Kymie M. C. Tan, Roy A.
Maxion, Jeannette M. Wing. &#8220;An Approach to Measuring A System&#8217;s Attack
Surface&#8221;. August 2007. CMU-CS-07-146.
<http://www.cs.cmu.edu/~wing/publications/CMU-CS-07-146.pdf>

\[McCabe1976\] McCabe, T.J. &#8220;A Complexity Measure&#8221;. IEEE Transactions on
Software Engineering. 1976-12. Volume 2, number 4. Pp. 308-320.

\[Punitha2013\] Punitha, K. and S. Chitra. Software defect prediction
using software metrics - A survey. International Conference on
Information Communication and Embedded Systems (ICICES). 2013.
2013-02-21 and -22.
http://ieeexplore.ieee.org/xpls/abs\_all.jsp?arnumber=6508369

\[Rodriguez2012\] Rodriguez, Daniel, Israel Herraiz, and Rachel
Harrison. &#8220;On Software Engineering Repositories and their Open Problems&#8221;
<http://promisedata.org/raise/2012/slides/RAISE12_Rguez.pdf>

\[Samoladas2004\] Samoladas, Ioannis, Ioannis Stamelos, Lefteris
Angelis, and Apostolos Oikonomou. &#8220;Open Source Software Development
Should Strive For Even Greater Code Maintainability.&#8221; *Communications of
the ACM*. Volume 47 Issue 10, October 2004. Pages 83-87.
<http://dl.acm.org/citation.cfm?id=1022598>

\[Schryen2009\] Schryen, Guido, and Rouven Kadura. &#8220;Open source vs.
closed source software: towards measuring security.&#8221; SAC &#8216;09 Proceedings
of the 2009 ACM symposium on Applied Computing. Pages 2016-2023. ACM New
York, NY, USA. ISBN: 978-1-60558-166-8 doi&gt;10.1145/1529282.1529731.
http://dl.acm.org/citation.cfm?id=1529731

\[Schryen2011\] Schryen, Guido. &#8220;Is Open Source Security a Myth?&#8221;
*Communications of the ACM*, Vol. 54 No. 5, Pages 130-140.
10.1145/1941487.1941516. May 2011.
<http://cacm.acm.org/magazines/2011/5/107687-is-open-source-security-a-myth/fulltext>

\[Schweik2012\] Schweik, Charles M. and Robert C. English. *Internet
Success*.

\[Shaikh2009\] Shaikh, Siraj A. and Antonio Cerone. Towards a metric for
Open Source Software Quality. ECEASST 2009. Volume 20.
<http://journal.ub.tu-berlin.de/eceasst/article/view/279/287>

\[Spinellis2009\] Spinellis, Diomidis, Georgios Gousios, Vassilios
Karakoidas, Panagiotis Louridas, Paul J. Adams, Ioannis Samoladas, and
Ioannis Stamelos. Evaluating the Quality of Open Source Software.
Electronic Notes in Theoretical Computer Science 233 (2009).

\[Wang2011\] Wang, Huanjing, Taghi M. Khoshgoftaar, and Naeem Seliya.
&#8220;How Many Software Metrics Should be Selected for Defect Prediction?&#8221;
2011. Association for the Advancement of Artificial Intelligence.
<http://www.aaai.org/ocs/index.php/flairs/flairs11/paper/download/2558/2993>

\[Wheeler2011e\] Wheeler, David A. *How to Evaluate Open Source Software
/ Free Software (OSS/FS) Programs*.
<http://www.dwheeler.com/oss_fs_eval.html>

\[Wheeler2014g\] Wheeler, David A. The Apple goto fail vulnerability:
lessons learned. 2014-11-27.
<http://www.dwheeler.com/essays/apple-goto-fail.html>

\[Wheeler2014h\] Wheeler, David A. *How to Prevent the next Heartbleed*.
2014-10-20. <http://www.dwheeler.com/essays/heartbleed.html>

\[Wheeler2014n\] Wheeler, David A. *Why Open Source Software / Free
Software (OSS/FS, FLOSS, or FOSS)? Look at the Numbers!*
<http://www.dwheeler.com/oss_fs_why.html>

\[Woody2014\] Woody, Carol, Robert Ellison, and William Nichols.
Predicting Software Assurance Using Quality and Reliability Measures.
December 2014. CMU/SEI-2014-TN-026.
<http://resources.sei.cmu.edu/library/asset-view.cfm?assetid=428589>


