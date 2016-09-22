# fs

This package provides a secure no-op version of the 'fs' package unpublished by npm, Inc.

Following the unpublishing incident (see report below), three versions of the *fs* package were then available in the npm repositories:

- fs@0.0.0 — uninstallable
- fs@0.0.1-security — inoperative placeholder
- fs@0.0.2 — re-published original (nuisance)

This version (fs@0.0.3-mjbrown) provides an empty *index.js* file to satisfy dependencies, yet eliminate the console log emitted by the original.

## [Incident report](http://status.npmjs.org/incidents/dw8cr1lwxkcr)

[**npm, Inc.**](http://status.npmjs.org/) issued the following [**incident report**](http://status.npmjs.org/incidents/dw8cr1lwxkcr) on Aug 23, 2016 - 20:34 UTC:

*For a few minutes today the package "fs" was unpublished from the registry in response to a user report that it was spam. It has been restored. This was a human error on my (@seldo's) part; I failed to properly follow our written internal process for checking if an unpublish is safe. My apologies to the users and builds we disrupted.*

*More detail: the "fs" package is a non-functional package. It simply logs the word "I am fs" and exits. There is no reason it should be included in any modules. However, something like 1000 packages *do* mistakenly depend on "fs", probably because they were trying to use a built-in node module called "fs". Given this, we should have deprecated the module instead of unpublishing it, and this is what our existing process says we should do.*

*If any of your modules are depending on "fs", you can safely remove it from your dependencies, and you should. But if you don't, things will continue to work indefinitely.*
