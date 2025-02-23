# dbt Core Changelog

- This file provides a full account of all changes to `dbt-core` and `dbt-postgres`
- Changes are listed under the (pre)release in which they first appear. Subsequent releases include changes from previous releases.
- "Breaking changes" listed under a version may require action from end users or external maintainers when upgrading to that version.
- Do not edit this file directly. This file is auto-generated using [changie](https://github.com/miniscruff/changie). For details on how to document a change, see [the contributing guide](https://github.com/dbt-labs/dbt-core/blob/main/CONTRIBUTING.md#adding-changelog-entry)

## dbt-core 1.4.0-b1 - December 15, 2022

### Features

- Added favor-state flag to optionally favor state nodes even if unselected node exists ([#2968](https://github.com/dbt-labs/dbt-core/issues/2968))
- Update structured logging. Convert to using protobuf messages. Ensure events are enriched with node_info. ([#5610](https://github.com/dbt-labs/dbt-core/issues/5610))
- Friendlier error messages when packages.yml is malformed ([#5486](https://github.com/dbt-labs/dbt-core/issues/5486))
- Migrate dbt-utils current_timestamp macros into core + adapters ([#5521](https://github.com/dbt-labs/dbt-core/issues/5521))
- Allow partitions in external tables to be supplied as a list ([#5929](https://github.com/dbt-labs/dbt-core/issues/5929))
- extend -f flag shorthand for seed command ([#5990](https://github.com/dbt-labs/dbt-core/issues/5990))
- This pulls the profile name from args when constructing a RuntimeConfig in lib.py, enabling the dbt-server to override the value that's in the dbt_project.yml ([#6201](https://github.com/dbt-labs/dbt-core/issues/6201))
- Adding tarball install method for packages. Allowing package tarball to be specified via url in the packages.yaml. ([#4205](https://github.com/dbt-labs/dbt-core/issues/4205))
- Added an md5 function to the base context ([#6246](https://github.com/dbt-labs/dbt-core/issues/6246))
- Exposures support metrics in lineage ([#6057](https://github.com/dbt-labs/dbt-core/issues/6057))
- Add support for Python 3.11 ([#6147](https://github.com/dbt-labs/dbt-core/issues/6147))
- incremental predicates ([#5680](https://github.com/dbt-labs/dbt-core/issues/5680))

### Fixes

- Account for disabled flags on models in schema files more completely ([#3992](https://github.com/dbt-labs/dbt-core/issues/3992))
- Add validation of enabled config for metrics, exposures and sources ([#6030](https://github.com/dbt-labs/dbt-core/issues/6030))
- check length of args of python model function before accessing it ([#6041](https://github.com/dbt-labs/dbt-core/issues/6041))
- Add functors to ensure event types with str-type attributes are initialized to spec, even when provided non-str type params. ([#5436](https://github.com/dbt-labs/dbt-core/issues/5436))
- Allow hooks to fail without halting execution flow ([#5625](https://github.com/dbt-labs/dbt-core/issues/5625))
- Clarify Error Message for how many models are allowed in a Python file ([#6245](https://github.com/dbt-labs/dbt-core/issues/6245))
- After this, will be possible to use default values for dbt.config.get ([#6309](https://github.com/dbt-labs/dbt-core/issues/6309))
- Use full path for writing manifest ([#6055](https://github.com/dbt-labs/dbt-core/issues/6055))
- [CT-1284] Change Python model default materialization to table ([#6345](https://github.com/dbt-labs/dbt-core/issues/6345))
- Repair a regression which prevented basic logging before the logging subsystem is completely configured. ([#6434](https://github.com/dbt-labs/dbt-core/issues/6434))

### Docs

- minor doc correction ([dbt-docs/#5791](https://github.com/dbt-labs/dbt-docs/issues/5791))
- Generate API docs for new CLI interface ([dbt-docs/#5528](https://github.com/dbt-labs/dbt-docs/issues/5528))
-  ([dbt-docs/#5880](https://github.com/dbt-labs/dbt-docs/issues/5880))
- Fix rendering of sample code for metrics ([dbt-docs/#323](https://github.com/dbt-labs/dbt-docs/issues/323))
- Alphabetize `core/dbt/README.md` ([dbt-docs/#6368](https://github.com/dbt-labs/dbt-docs/issues/6368))

### Under the Hood

- Put black config in explicit config ([#5946](https://github.com/dbt-labs/dbt-core/issues/5946))
- Added flat_graph attribute the Manifest class's deepcopy() coverage ([#5809](https://github.com/dbt-labs/dbt-core/issues/5809))
- Add mypy configs so `mypy` passes from CLI ([#5983](https://github.com/dbt-labs/dbt-core/issues/5983))
- Exception message cleanup. ([#6023](https://github.com/dbt-labs/dbt-core/issues/6023))
- Add dmypy cache to gitignore ([#6028](https://github.com/dbt-labs/dbt-core/issues/6028))
- Provide useful errors when the value of 'materialized' is invalid ([#5229](https://github.com/dbt-labs/dbt-core/issues/5229))
- Clean up string formatting ([#6068](https://github.com/dbt-labs/dbt-core/issues/6068))
- Fixed extra whitespace in strings introduced by black. ([#1350](https://github.com/dbt-labs/dbt-core/issues/1350))
- Remove the 'root_path' field from most nodes ([#6171](https://github.com/dbt-labs/dbt-core/issues/6171))
- Combine certain logging events with different levels ([#6173](https://github.com/dbt-labs/dbt-core/issues/6173))
- Convert threading tests to pytest ([#5942](https://github.com/dbt-labs/dbt-core/issues/5942))
- Convert postgres index tests to pytest ([#5770](https://github.com/dbt-labs/dbt-core/issues/5770))
- Convert use color tests to pytest ([#5771](https://github.com/dbt-labs/dbt-core/issues/5771))
- Add github actions workflow to generate high level CLI API docs ([#5942](https://github.com/dbt-labs/dbt-core/issues/5942))
- Functionality-neutral refactor of event logging system to improve encapsulation and modularity. ([#6139](https://github.com/dbt-labs/dbt-core/issues/6139))
- Consolidate ParsedNode and CompiledNode classes ([#6383](https://github.com/dbt-labs/dbt-core/issues/6383))
- Prevent doc gen workflow from running on forks ([#6386](https://github.com/dbt-labs/dbt-core/issues/6386))
- Fix intermittent database connection failure in Windows CI test ([#6394](https://github.com/dbt-labs/dbt-core/issues/6394))
- Refactor and clean up manifest nodes ([#6426](https://github.com/dbt-labs/dbt-core/issues/6426))
- Restore important legacy logging behaviors, following refactor which removed them ([#6437](https://github.com/dbt-labs/dbt-core/issues/6437))

### Dependencies

- Update pathspec requirement from ~=0.9.0 to >=0.9,<0.11 in /core ([#5917](https://github.com/dbt-labs/dbt-core/pull/5917))
- Bump black from 22.8.0 to 22.10.0 ([#6019](https://github.com/dbt-labs/dbt-core/pull/6019))
- Bump mashumaro[msgpack] from 3.0.4 to 3.1.1 in /core ([#6108](https://github.com/dbt-labs/dbt-core/pull/6108))
- Update colorama requirement from <0.4.6,>=0.3.9 to >=0.3.9,<0.4.7 in /core ([#6144](https://github.com/dbt-labs/dbt-core/pull/6144))

### Dependency

- Bump mashumaro[msgpack] from 3.1.1 to 3.2 in /core ([#4904](https://github.com/dbt-labs/dbt-core/issues/4904))

### Contributors
- [@andy-clapson](https://github.com/andy-clapson) ([dbt-docs/#5791](https://github.com/dbt-labs/dbt-docs/issues/5791))
- [@chamini2](https://github.com/chamini2) ([#6041](https://github.com/dbt-labs/dbt-core/issues/6041))
- [@daniel-murray](https://github.com/daniel-murray) ([#2968](https://github.com/dbt-labs/dbt-core/issues/2968))
- [@dave-connors-3](https://github.com/dave-connors-3) ([#5990](https://github.com/dbt-labs/dbt-core/issues/5990))
- [@dbeatty10](https://github.com/dbeatty10) ([dbt-docs/#6368](https://github.com/dbt-labs/dbt-docs/issues/6368), [#6394](https://github.com/dbt-labs/dbt-core/issues/6394))
- [@devmessias](https://github.com/devmessias) ([#6309](https://github.com/dbt-labs/dbt-core/issues/6309))
- [@eve-johns](https://github.com/eve-johns) ([#6068](https://github.com/dbt-labs/dbt-core/issues/6068))
- [@haritamar](https://github.com/haritamar) ([#6246](https://github.com/dbt-labs/dbt-core/issues/6246))
- [@jared-rimmer](https://github.com/jared-rimmer) ([#5486](https://github.com/dbt-labs/dbt-core/issues/5486))
- [@josephberni](https://github.com/josephberni) ([#2968](https://github.com/dbt-labs/dbt-core/issues/2968))
- [@joshuataylor](https://github.com/joshuataylor) ([#6147](https://github.com/dbt-labs/dbt-core/issues/6147))
- [@justbldwn](https://github.com/justbldwn) ([#6245](https://github.com/dbt-labs/dbt-core/issues/6245))
- [@luke-bassett](https://github.com/luke-bassett) ([#1350](https://github.com/dbt-labs/dbt-core/issues/1350))
- [@max-sixty](https://github.com/max-sixty) ([#5946](https://github.com/dbt-labs/dbt-core/issues/5946), [#5983](https://github.com/dbt-labs/dbt-core/issues/5983), [#6028](https://github.com/dbt-labs/dbt-core/issues/6028))
- [@paulbenschmidt](https://github.com/paulbenschmidt) ([dbt-docs/#5880](https://github.com/dbt-labs/dbt-docs/issues/5880))
- [@pgoslatara](https://github.com/pgoslatara) ([#5929](https://github.com/dbt-labs/dbt-core/issues/5929))
- [@racheldaniel](https://github.com/racheldaniel) ([#6201](https://github.com/dbt-labs/dbt-core/issues/6201))
- [@timle2](https://github.com/timle2) ([#4205](https://github.com/dbt-labs/dbt-core/issues/4205))
- [@dave-connors-3](https://github.com/dave-connors-3) ([#5680](https://github.com/dbt-labs/dbt-core/issues/5680))


## Previous Releases

For information on prior major and minor releases, see their changelogs:


* [1.3](https://github.com/dbt-labs/dbt-core/blob/1.3.latest/CHANGELOG.md)
* [1.2](https://github.com/dbt-labs/dbt-core/blob/1.2.latest/CHANGELOG.md)
* [1.1](https://github.com/dbt-labs/dbt-core/blob/1.1.latest/CHANGELOG.md)
* [1.0](https://github.com/dbt-labs/dbt-core/blob/1.0.latest/CHANGELOG.md)
* [0.21](https://github.com/dbt-labs/dbt-core/blob/0.21.latest/CHANGELOG.md)
* [0.20](https://github.com/dbt-labs/dbt-core/blob/0.20.latest/CHANGELOG.md)
* [0.19](https://github.com/dbt-labs/dbt-core/blob/0.19.latest/CHANGELOG.md)
* [0.18](https://github.com/dbt-labs/dbt-core/blob/0.18.latest/CHANGELOG.md)
* [0.17](https://github.com/dbt-labs/dbt-core/blob/0.17.latest/CHANGELOG.md)
* [0.16](https://github.com/dbt-labs/dbt-core/blob/0.16.latest/CHANGELOG.md)
* [0.15](https://github.com/dbt-labs/dbt-core/blob/0.15.latest/CHANGELOG.md)
* [0.14](https://github.com/dbt-labs/dbt-core/blob/0.14.latest/CHANGELOG.md)
* [0.13](https://github.com/dbt-labs/dbt-core/blob/0.13.latest/CHANGELOG.md)
* [0.12](https://github.com/dbt-labs/dbt-core/blob/0.12.latest/CHANGELOG.md)
* [0.11 and earlier](https://github.com/dbt-labs/dbt-core/blob/0.11.latest/CHANGELOG.md)
