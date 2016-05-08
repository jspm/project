jspm Project Roadmap
===

This roadmap represents the current core development directions of the jspm project.

> The biggest single contribution users can help make to the jspm project is by working on issues, bugs and features
that **are not necesarily related to this roadmap**. That is because you have a unique understanding of what is lacking in the project,
that would be great to hear. [See CONTRIBUTING.md for more information here](CONTRIBUTING.md).

### 2016 Goals:

1. jspm 0.17 launch
2. Comprehensive SystemJS documentation update
3. SystemJS Builder API documentation
4. SystemJS 0.20
5. jspm 0.18 on SystemJS 0.20

The above goals may well change, but are currently regarded as the primary development priorities for 2016, with the hope
to be able to complete all of the above before the end of 2016. This may or may not turn out to be overly ambitious.

## 1. jspm 0.17 launch

Tracking at https://github.com/jspm/jspm-cli/pull/1099.

The jspm 0.17 release is currently pending the following:

- [ ] Straightforward 0.17 API documentation update
- [ ] Refining init workflow
- [x] Checking source maps
- [ ] Investigate test and coverage workflows
- [x] Handling development install trees
- [x] Peer dependency conflict refinement
- [ ] General stability and feedback

> Beta feedback, and discussions around the above points are very welcome.

## 2. Comprehensive SystemJS documentation update

Tracking at https://github.com/systemjs/systemjs/pull/1143.

The goal is to provide both a comprehensive API documentation as well as more tutorial-format articles, with cross-linking
between the two. Documentation aims to cover the full architecture of the project, providing both complete high-level and low-level
understanding. The rough structure is in place at the moment, but there is a lot still to fill in.

> Extensions in the mean time to the existing documentation are very welcome pending this PR.

## 3. SystemJS Builder API documentation

Tracking at https://github.com/systemjs/builder/issues/250.

> API documentation contributions are very welcome pending this PR.

## 4. SystemJS 0.20

SystemJS 0.20 would be a deprecation release, and would solidify the SystemJS API.

It may be possible to delay this release for other core goals, but at the same time SystemJS is the core foundation of the jspm project,
and also a project with a user base of its own. Prioritising this foundational stability has always been a key development goal in jspm.

Reasons for prioritising this update include:
* SystemJS still runs the older module loader spec. Updating to the WhatWG loader spec would be important for the project.
  The risk here is loader spec stability of course.
* SystemJS needs to use its own global not called `System` for forwards compatibility reasons (`System` is a reserved global in new specs
  in the browser). The current plan here is to deprecate the `System` global for the `SystemJS` global (both are currently support).
* The WhatWG specification is also a much smaller implementation, and can drop support for older browsers (IE8), so that it will reduce
  the size of the project and improve performance (which is a crucial concern).

Unfortunately this work is very much architectural in nature, and will appear mostly invisible to users apart from the
API name changes (eg System -> SystemJS, System.normalize -> SystemJS.resolve etc).

## 5. jspm 0.18 on SystemJS 0.20

Having updates SystemJS to 0.20, rolling this upgrade through into jspm 0.18 would be the next priority.
