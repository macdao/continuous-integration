# Continuous Integration


## Concept

- a software development practice
- members of a team integrate their work frequently
- usually each person integrates at least daily - leading to multiple integrations per day
- Each integration is verified by an automated build (including test) to detect integration errors as quickly as possible


- Many teams find that this approach leads to significantly reduced integration problems
- and allows a team to develop cohesive software more rapidly


- The term 'Continuous Integration' originated with the Extreme Programming development process
- as one of its original twelve practices



## Martin's first sightings of a large software project 

- had been in development for a couple of years and was currently integrating
- and had been integrating for several months
- nobody really knew how long it would take to finish integrating
- learned a common story of software projects: integration is a long and unpredictable process.



## Practices of Continuous Integration


### Maintain a Single Source Repository

- Source Code Management tools
  - Subversion
  - Git
- put everything required for a build in the source control system

  The basic rule of thumb is that you should be able to walk up to the project with a virgin machine, do a checkout, and be able to fully build the system
- a single branch
- store nothing that you actually build


### Automate the Build

- Automated environments for builds
  - Ant
  - Maven
  - Gradle
- A common mistake is not to include everything in the automated build

  anyone should be able to bring in a virgin machine, check the sources out of the repository, issue a single command, and have a running system on their machine
- IDEs


### Make Your Build Self-Testing

- A program may run, but that doesn't mean it does the right thing
- include automated tests in the build process to catch bugs more quickly and efficiently
- For a build to be self-testing the failure of a test should cause the build to fail
- JUnit
- Mockito
- Cucumber
- Capybara


### Everyone Commits To the Mainline Every Day

- Integration is primarily about communication
- As with any commit cycle the developer
  - updates their working copy to match the mainline
  - resolves any conflicts with the mainline
  - builds on their local machine
  - If the build passes, then they are free to commit to the mainline
- Conflicts that stay undetected for weeks can be very hard to resolve
- Frequent commits encourage developers to break down their work into small chunks of a few hours each


### Every Commit Should Build the Mainline on an Integration Machine

- mainline stays in a healthy state (however, things still do go wrong)
  1. discipline, people not doing an update and build before they commit
  2. environmental differences between developers' machines
- continuous integration server: Bamboo, Jenkins, Go
- the developer who commits is responsible for this (build succeeds)
- Nightly builds


### Fix Broken Builds Immediately

- The whole point of working with CI is that you're always developing on a known stable base
- `"nobody has a higher priority task than fixing the build"` - remember Kent Beck


### Keep the Build Fast

- the XP guideline of a ten minute build is perfectly within reason
- deployment pipeline/two stage deployment pipeline
  - commit build
  - The second stage build
- If the secondary build detects a bug, that's a sign that the commit build could do with another test


### Test in a Clone of the Production Environment

- test doubles
- virtualization


### Make it Easy for Anyone to Get the Latest Executable


### Everyone can see what's happening

- Continuous Integration is all about communication
- state of the mainline build
- not co-located can get a sense of the project's status


### Automate Deployment



## Benefits of Continuous Integration

- reduced risk
- Continuous Integrations doesn't get rid of bugs, but it does make them dramatically easier to find and remove
- the degree of this benefit(less bugs)) is directly tied to how good your test suite is
- Frequent deployment



## References

- http://www.martinfowler.com/articles/continuousIntegration.html



## Further Reading

- http://www.thoughtworks.com/continuous-integration
- http://www.martinfowler.com/bliki/FeatureToggle.html
- http://www.martinfowler.com/bliki/FeatureBranch.html
- http://www.martinfowler.com/bliki/TestDouble.html
- http://www.martinfowler.com/bliki/PendingHead.html
- http://www.extremeprogramming.org/
- https://github.com/dreamhead/moco
