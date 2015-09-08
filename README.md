# perl-package-tests
Tests for perl packages I'm always creating in some way or other.

### Why?
[ Dist::Zilla ](http://dzil.org/) does a lot of work for you, including creating
tests.

But Dist::Zilla doesn't enforce any standards for the tests, and I frequently
work on projects where I'm not able to use Dist::Zilla for one reason or
another.

I found myself copying tests from various places, and not always the right
ones, or all of the tests I needed to include to make good code. So, I created
this repository.

### Install
XXX: There is a way to just export the xt directory ... need to include
instructions here.

Maybe
[this](http://stackoverflow.com/questions/160608/do-a-git-export-like-svn-export)
has something.

### Tests
Currently included tests are listed and described below but the actual
contents of the xt directory are authoritative, not this document.

Check the individual files for details on what each test is checking for.

I'm trying to follow the definitions from (The Lancaster
Consensus)[https://github.com/Perl-Toolchain-Gang/toolchain-site/blob/master/lancaster-consensus.md#environment-variables-for-testing-contexts]
for different types of tests.

These tests are not necessarily categorized according to these definitions. I'm working on fixing that.

#### Author Tests
`AUTHOR_TESTING`: if true, tests are being run as part of an author's personal
development process; such tests may or may not be run prior to release.  CPAN
clients must not set this variable.  Distribution packagers (ppm, deb, rpm,
etc.) should not set this variable.

* [Check Dependencies](xt/author/checkdeps.t)
* [Check for common spelling mistakes](xt/author/spelling_commonmistakes.t)
* [Check for errors in POD](xt/author/pod.t)
* [Check spelling](xt/author/spelling.t)
* [Consistent Version Numbers](xt/author/consistentversion.t)
* [Correct EOF](xt/author/eof.t)
* [Correct EOLs](xt/author/eol.t)
* [Is there a synopsis?](xt/author/synopsis.t)
* [Is there a version number?](xt/author/version.t)
* [No Tabs!](xt/author/notabs.t)
* [POD Coverage](xt/author/pod_coverage.t)

#### Release Tests

`RELEASE_TESTING`: if true, tests are being run as part of a release QA
process; CPAN clients must not set this variable.

* [Were changes noted in the Changes file?](xt/release/check-changes.t)
* [Is the manifest correct?](xt/release/check-manifest.t)
* [Are namespaces clean?](xt/release/clean_namespaces.t)
* [Do scripts compile and run ok?](xt/release/cmd.t)
* [Do packages compile?](xt/release/compile.t)
* [Is there a CPAN changes file?](xt/release/cpan-changes.t)
* [Another manifest check](xt/release/dist-manifest.t)
* [Is CPAN meta information accurate?](xt/release/distmeta.t)
* [Were any fixme notes left in the code?](xt/release/fixme.t)
* [Does the package have a version number?](xt/release/has-version.t)
* [Does the package pass kwalitee tests?](xt/release/kwalitee.t)
* [Do the modules load?](xt/release/load.t)
* [Is META.json created correctly?](xt/release/meta-json.t)
* [Are minimum version for required libraries correct?](xt/release/minimum-version.t)
* [Did you forget a $DB::single?](xt/release/nobreakpoints.t)
* [Don't leave smart comments in code](xt/release/no-smart-comments.t)
* [Are PAUSE permissions set up correctly?](xt/release/pause-permissions.t)
* [Does code use best practices?](xt/release/perlcritic.t)
* [Experimental version of best practices check](xt/release/perllint.t)
* [Are POD links working?](xt/release/pod-linkcheck.t)
* [Are there any broken sites we are linking to?](xt/release/pod-no404s.t)
* [Are all prerequisites installed and accounted for?](xt/release/prereq.t)
* [Does this package has appropriate legal information?](xt/release/test-legal.t)
* [Are there any variables that are unused?](xt/release/vars.t)

#### Automated TEsts
`AUTOMATED_TESTING`: if true, tests are being run by an automated testing
facility and not as part of the installation of a module; CPAN smokers must
set this to true; CPAN clients must not set this.

#### Non-interactive Tests
`NONINTERACTIVE_TESTING`: if true, tests should not attempt to interact with
a user; output may not be seen and prompts will not be answered.

#### Extended Tests
`EXTENDED_TESTING`: if true, the user or process running tests is willing to
run optional tests that may take extra time or resources to complete.  Such
tests must not include any development or QA tests.  Only tests of runtime
functionality should be included.

