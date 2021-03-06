## Changelog

### [0.19.0] (unreleased)

- Bring back `+reagent` / `--reagent` for compatibility

### [0.18.0] - 2019-04-03

- Update CIDER vars in dir-locals.el
- Bump Piggieback for latest jvm support

### [0.17.0] - 2019-01-01

- Drop Om, replace Reagent as the default UI library
- Update critically breaking dependencies
- Add javax xml bind dependency to fix Java 9+ compatability
- Explicitly add dotfiles to project for lein compatability
- Bump dependencies so project flags work out of the box

### [0.16.0] - 2018-05-06

- Add `+edge` and `+bleeding-edge` options for automatically using the latest version of dependencies.
- Upgrade ClojureScript, Om, Reagent, lein-cljsbuild, Figwheel
- Fix middleware order so static files correctly have their media type set
- Bring back logging to file, using [clj-logging-config](https://github.com/malcolmsparks/clj-logging-config)
- Add a help screen (`+help` or when using any unrecognized options)
- Set `goog.DEBUG` to `false` in the production ClojureScript build
- Fix lein 1.8 compatability
- Fix Procfile rendering

### [0.15.2] - 2017-07-30

- Update more docs to refer to `(go)` and `(cljs-repl)` instead of `(run)` and `(browser-repl)`
- Fix less and sass support
- Fix `index.html` generation when project name contains an underscore
- Upgrade several versions (ClojureScript, Ring, lein-cljsbuild, re-frame, piggieback, ring.middleware.logger)

### [0.15.1] - 2017-05-29

- Make the pop-poll work by shelling out to curl

### [0.15.0] - 2017-05-29

- Add Component support, both backend and frontend
- Add a `+re-frame` flag, for [re-frame](https://github.com/Day8/re-frame) projects
- remove `:repl-options {:init (go)}` from `project.clj`. You'll have to call `(go)` yourself after starting a REPL
- clean up the SASS/LESS support. It's still a hack, but a slightly cleaner hack
- Make `code_of_conduct.md` optional (`+coc` or `+code-of-conduct` flag to add it back)
- Make `browser-repl` and `run` deprecated, in favor of `cljs-repl` and `go`
- Collect usage statistics (version + command line flags). It is possible to opt-out with `+no-poll`.
- Bump versions: clojurescript 1.9.562, transit-clj 0.8.300, ring 1.6.1, ring-defaults 0.3.0, compojure 1.6.0, figwheel 0.5.10, figwheel-sidecar 0.5.10, org.clojure/tools.nrepl 0.2.13, om 1.0.0-alpha48

### 0.15.0-SNAPSHOT

- Options now use `+` as a prefix instead of `--`. This is more in line with
  other popular templates like Luminus, and it stops Leiningen from eating our
  options. The `--` variants still work.
- Add Rum support. Use (`+rum`).
- Add Om Next support. Use (`+om-next`).
- Bump versions: clojurescript 1.9.293, transit-clj 0.8.297, ring 1.5.0, ring-defaults 0.2.1, compojure 1.5.1, environ 1.1.0, reagent 0.6.0, figwheel 0.5.8, http-kit 2.2.0, om 1.0.0-alpha47, doo 0.1.7, lein-cljsbuild 1.1.5, lein-environ 1.1.0

### [0.14.0] - 2016-06-23

- Add cljc support
- ClojureScript 1.9.89
- Figwheel 0.5.4-4

### [0.13.0] - 2016-06-13

- Clojurescript 1.9.36
- Include Transit for faster ClojureScript compilation
- Figwheel 0.5.4-2
- Reagent 0.6.0-rc
- Om 1.0.0-alpha36
- Avoid using Leiningen profile merging for `:cljsbuild` configs

### [0.12.0] - 2016-05-24

* Upgrades
  * org.omcljs/om 1.0.0-alpha31 => 1.0.0-alpha35
  * lein-auto 0.1.1 => 0.1.2
  * lein-less 1.7.3 => 1.7.5
  * org.clojure/clojurescript 1.8.40 => 1.8.51
  * environ 1.0.2 => 1.0.3
  * lein-cljsbuild 1.1.1 => 1.1.3
  * lein-environ 1.0.1 => 1.0.3
  * figwheel 0.5.2 => 0.5.3-2
* Only add "dev" to the classpath in dev mode, fixes an issue with `lein jar`

### [0.11.0] - 2016-03-28

* Upgrade ClojureScript 1.7.228 => 1.8.40
* Upgrade Figwheel 0.5.1 => 0.5.2

### [0.10.1] - 2016-03-27

* Fix missing dependency when using `--http-kit`

### 0.10.0 - 2016-03-24

* Add switches for --reagent and --vanilla
* Upgrade Figwheel to 0.5.1
* Upgrade to Clojure 1.8.0, Om 1.1.0-alpha31, ring-defaults 0.2.0, compojure 1.5.0

### v0.9.1 - 2016-02-02

* Upgrade Figwheel to 0.5.0-6
* Upgrade Environ to 1.0.2
* Upgrade internal dependencies to play better with Boot

### v0.9.0 - 2016-01-29

* Use Figwheel for REPL and Ring server
* Remove boilerplate that's no longer needed
* Drop Enlive and simplify the dev setup
* Drop CLJX support
* Better inline documentation
* Upgrade all dependencies

### v0.8.2-SNAPSHOT
* Version upgrades: clojurescript: 1.7.145 => 1.7.189, om: 1.0.0-alpha15 => 1.0.0-alpha28, figwheel => 0.4.1, figwheel-sidecar 0.4.1 => 0.5.0-2, lein-figwheel 0.4.1 =>  0.5.0-2
* Version upgrades: clojurescript: 1.7.122 => 1.7.145, om: 0.9.0 => 1.0.0-alpha15, tools.nrepl => 0.2.12, figwheel => 0.4.1, figwheel-sidecar => 0.4.1, lein-figwheel => 0.4.1,environ => 1.0.1, lein-environ => 1.0.1
* Fix allowing projects to have - in their names.
* Fix allowing groupID/artifactID naming convention.
* Fix "No such namespace" when using om via the REPL.
* Fix specljs auto testing.
* Added gzip compression using [ring.middleware.gzip](https://github.com/bertrandk/ring-gzip).
* Added browser cache-control hinting using [ring.middleware.browser-caching](https://github.com/slester/browser-caching).
* Version upgrades: clojure: 1.6.0 => 1.7.0, clojurescript: 0.0-3058 => 1.7.48, ring: 1.3.2 => 1.4.0, ring-defaults: 0.1.4 => 0.1.5, compojure: 1.3.2 => 1.4.0, om: 0.8.8 => 0.9.0, figwheel: 0.2.5 => 0.3.7, piggieback: 0.1.5 => 0.2.1, weasel: 0.6.0 => 0.7.0

### v0.8.1

* Restore working lein repl for cljx projects ([Josh Daghlian](https://github.com/jcdcodes))
* Use latest version of enlive to fix windows issue ([Justin Squirek](https://github.com/AdaDoom3))

### v0.8.0

* Update Om: 0.8.0-rc1 => 0.8.8 ([Anna Pawlicka](https://github.com/annapawlicka))
* Make Uberjar executable ([B??rge Svingen](https://github.com/bsvingen))
* Remove react.js injection in dev html ([Jamie English](https://github.com/english))
* Fix how Less and Sassc are invoked ([Daryl Lau](https://github.com/dlau))
* Fix in figwheel config ([Tim Gilbert](https://github.com/timgilbert)), ([Philip Joseph](https://github.com/lambdahands)), ([Antony Woods](https://github.com/acron0))
* Fix in test setup ([Geoff Shannon](https://github.com/RadicalZephyr))
* Doc fixes ([Anthony Rosequist](https://github.com/arosequist))
* Version upgrades: clojurescript: 0.0-2511 => 0.0-3058 ; figwheel: 0.2.1-SNAPSHOT => 0.2.5 ; weasel: 0.4.2 => 0.6.0 and more

### v0.7.0 - 2015-03-06

* Added Clojure{,script} unit testing support with Phantom JS.
  ([Rory Gibson](https://github.com/rorygibson))
* Update om-tools: 0.3.9 => 0.3.10
* Update ring-defaults: 0.1.2 => 0.1.3
* Use figwheel-sidecar, drop the dependency on leiningen
* renamed the per-env namespace from dev to main
* give a proper error message when trying to invoke less in production

### v0.7.0-SNAPSHOT-20150103 - 2015-01-03

* Validate command line arguments
* Mention Chestnut version in the generated README
* Fix om-tools support
* SASSC support has been fixed, but is considered undocumented and unsupported
* Update Om: 0.7.0 =>  0.8.0-rc1
* Add Code of Conduct to generated projects
* Update CLJX: 0.4.0 =>  0.5.0
* Update Clojurescript: 0.0-2496 => 0.0-2644
* Fixes for regressions: [#71](https://github.com/plexus/chestnut/pull/71)

### v0.7.0-SNAPSHOT-20141226 - 2014-12-26

* Update Clojurescript: 0.0-2371 =>  0.0-2496
* Update Compojure: 1.2.0 =>  1.3.1
* Update Om: 0.7.0 =>  0.8.0-beta3
* Fixes for regressions: [#65](https://github.com/plexus/chestnut/pull/65) [#57](https://github.com/plexus/chestnut/pull/57)

### v0.7.0-SNAPSHOT-20141207 - 2014-12-07

* Make weasel print both to the REPL and the browser console
  ([Marcus Lewis](https://github.com/mrcslws))
* Add support for the LESS CSS pre-processor
  ([Denis Golovnev](https://github.com/teur))
* Enable auto-reload of enlive templates in dev mode
  ([Ray H](https://github.com/rymndhng))
* Add support for the SASS CSS pre-processor
  ([Edward Wible](https://github.com/aew))
* Add suport for Speclj ([Edward Wible](https://github.com/aew))
* Switch from the deprecated compojure.handler to ring-defaults
  [zakak](https://github.com/zakak))
* Keep dev dependencies (Leiningen, Figwheel, Weasel, Speclj) out of
  the Uberjar
* Automatically switch the browser-repl to the right namespace after
  starting up, instead of `cljs.user`
* No longer include lein-ancient, easy enough to add for those that
  want it
* Update Ring: 1.3.1 => 1.3.2
* Update Figwheel: 0.1.4-SNAPSHOT => 0.1.6-SNAPSHOT
* Update Weasel: 0.4.0-SNAPSHOT => 0.4.2

### v0.6.0 - 2014-10-29

* Add optional support for CLJX
  ([Olli Piepponen](https://github.com/luxbock))
* Support generation of projects named using the groupId/artifactId
  convention (e.g. com.example/foo)
  ([Steeve Beliveau](https://github.com/stebel))

### v0.5.0 - 2014-10-10

* Run figwheel inside `(run)` so we only need one process
* Configure figwheel's CSS reloading and load a placeholder
  `style.css`
* Refresh Om when Figwheel reloads
* Update ClojureScript: 0.0-2342 => 0.0-2371
* Update Compojure: 1.1.9 => 1.2.0
* Update Om: 0.7.1 => 0.7.3
* No longer depend on Weasel in production mode

### v0.4.0 - 2014-09-27

* Option to switch to HTTP Kit for a web server
* Add reloading middleware
* Add default compojure.handler.site middleware

### v0.3.0 - 2014-09-26

* Switched to Weasel for Austin
* Optimized uberjar
* Fix usage of {{name}}/{{sanitized}}
* Load react from the jar, instead of from Facebook's CDN
* Update dependencies (Clojurescript, Ring, Compojure, Environ)

### v0.2.0 - 2014-09-21

* Uberjar support
* Heroku support (Procfile, system.properties)
* added .gitignore
* First version of development/production modes

### v0.1.0 - 2015-09-19

* First release, containing Austin, Figwheel, Om

[Unreleased]: https://github.com/plexus/chestnut/compare/v0.15.2...HEAD
[0.15.2]: https://github.com/plexus/chestnut/compare/v0.15.1...v0.15.2
[0.15.1]: https://github.com/plexus/chestnut/compare/v0.15.0...v0.15.1
[0.15.0]: https://github.com/plexus/chestnut/compare/v0.14.0...v0.15.0
[0.14.0]: https://github.com/plexus/chestnut/compare/v0.13.0...v0.14.0
[0.13.0]: https://github.com/plexus/chestnut/compare/v0.12.0...v0.13.0
[0.12.0]: https://github.com/plexus/chestnut/compare/v0.11.0...v0.12.0
[0.11.0]: https://github.com/plexus/chestnut/compare/v0.10.1...v0.11.0
[0.10.1]: https://github.com/plexus/chestnut/compare/v0.10.0...v0.10.1
