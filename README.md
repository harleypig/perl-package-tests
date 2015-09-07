# perl-package-tests
Tests for perl packages I'm always creating in some way or other.

## Why?
(Dist::Zilla)[http://dzil.org/] does a lot of work for you, including creating
tests.

But Dist::Zilla doesn't enforce any standards for the tests, and I frequently
work on projects where I'm not able to use Dist::Zilla for one reason or
another.

I found myself copying tests from various places, and not always the right
ones, or all of the tests I needed to include to make good code. So, I created
this repository.

## Install
XXX: There is a way to just export the xt directory ... need to include
instructions here.

Maybe
(this)[http://stackoverflow.com/questions/160608/do-a-git-export-like-svn-export]
has something.

## Tests
Currently included tests are listed and described below but the actual
contents of the xt directory are authoritative, not this document.

### Author Tests
Author tests should check documentation, formatting, spelling. Generally,
tests for things that don't affect execution of the code.

* [Check Dependencies](xt/author/checkdeps.t)
* consistentversion.t
* eof.t
* eol.t
* notabs.t
* pod_coverage.t
* pod.t
* spelling_commonmistakes.t
* spelling.t
* synopsis.t
* version.t

### Release Tests
Release tests should check for things that can effect run-time execution of
the code, but that aren't usually caught with a simple syntax check. Best
practices should also be checked here.

* check-changes.t
* check-manifest.t
* clean_namespaces.t
* cmd.t
* compile.t
* cpan-changes.t
* dist-manifest.t
* distmeta.t
* fixme.t
* has-version.t
* kwalitee.t
* load.t
* meta-json.t
* minimum-version.t
* nobreakpoints.t
* no-smart-comments.t
* pause-permissions.t
* perlcritic.t
* perllint.t
* pod-linkcheck.t
* pod-no404s.t
* prereq.t
* test-legal.t
* vars.t
