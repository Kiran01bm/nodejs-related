## yarn/yarn-ver1

node_modules way

```
ζ git clone https://github.com/yarnpkg/example-yarn-package.git
Cloning into 'example-yarn-package'...
remote: Enumerating objects: 31, done.
remote: Total 31 (delta 0), reused 0 (delta 0), pack-reused 31
Unpacking objects: 100% (31/31), done.

ζ cd example-yarn-package

ζ yarn --version                                                                                                                                                                                                

1.22.4

ζ yarn install                                                                                                                                                                                                                     [0b8f43f]
yarn install v1.22.4
[1/4] 🔍  Resolving packages...
[2/4] 🚚  Fetching packages...
[3/4] 🔗  Linking dependencies...
[4/4] 🔨  Building fresh packages...
warning Your current version of Yarn is out of date. The latest version is "1.22.5", while you're on "1.22.4".
info To upgrade, run the following command:
$ brew upgrade yarn
✨  Done in 18.13s.

ζ ls -lart                                                                                                                                                                                                                         [0b8f43f]
total 184
drwxr-xr-x  192 kiran  project   6144  7 Sep 11:50 ..
-rw-r--r--    1 kiran  project     14  7 Sep 11:50 .gitignore
-rw-r--r--    1 kiran  project   1346  7 Sep 11:50 LICENSE
-rw-r--r--    1 kiran  project   2080  7 Sep 11:50 README.md
drwxr-xr-x    3 kiran  project     96  7 Sep 11:50 __tests__
-rw-r--r--    1 kiran  project    253  7 Sep 11:50 index.js
-rw-r--r--    1 kiran  project    485  7 Sep 11:50 package.json
-rw-r--r--    1 kiran  project  70479  7 Sep 11:50 yarn.lock
drwxr-xr-x   11 kiran  project    352  7 Sep 11:50 .
drwxr-xr-x  328 kiran  project  10496  7 Sep 11:51 node_modules
drwxr-xr-x   12 kiran  project    384  7 Sep 11:51 .git
```

## yarn/yarn-ver2

### Plug'n'Play

RIP node_modules - In this install mode (now the default starting from Yarn v2), Yarn generates a single .pnp.js file instead of the usual node_modules. Instead of containing the source code of the installed packages, the .pnp.js file contains a map linking a package name and version to a location on the disk, and another map linking a package name and version to its set of dependencies. Thanks to this efficient system, Yarn can tell Node exactly where to look for files being required - regardless of who asks for them!


```
ζ git clone https://github.com/yarnpkg/example-yarn-package.git
Cloning into 'example-yarn-package'...
remote: Enumerating objects: 31, done.
remote: Total 31 (delta 0), reused 0 (delta 0), pack-reused 31
Unpacking objects: 100% (31/31), done.


ζ ls -lart
total 0
drwxr-xr-x   4 kiran  project  128  7 Sep 11:53 ..
drwxr-xr-x   3 kiran  project   96  7 Sep 11:55 .
drwxr-xr-x  10 kiran  project  320  7 Sep 11:55 example-yarn-package


ζ cd example-yarn-package

ζ yarn policies set-version berry                                                                                                                                                                                                  
Resolving berry to a url...
Downloading https://github.com/yarnpkg/berry/raw/master/packages/berry-cli/bin/berry.js...
Saving it into /Users/kiran/Documents/yarn/yarn-ver2/example-yarn-package/.yarn/releases/yarn-berry.js...
Updating /Users/kiran/Documents/yarn/yarn-ver2/example-yarn-package/.yarnrc.yml...
Done!

ζ yarn set version berry                                                                                                                                                                                                           [0b8f43f]
➤ YN0000: Downloading https://github.com/yarnpkg/berry/raw/master/packages/yarnpkg-cli/bin/yarn.js
➤ YN0000: Saving the new release in .yarn/releases/yarn-2.2.2.cjs
➤ YN0000: Done in 1.25s

ζ yarn --version                                                                                                                                                                                                 
2.2.2

ζ gs                                                                                                                                                                                                             
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	.yarn/
	.yarnrc.yml

ζ yarn install                                                                                                                                                                                                                     [0b8f43f]
➤ YN0000: ┌ Resolution step
➤ YN0061: │ mkdirp@npm:0.5.1 is deprecated: Legacy versions of mkdirp are no longer supported. Please update to mkdirp 1.x. (Note that the API surface has changed to use Promises in 1.x.)
➤ YN0061: │ mkdirp@npm:0.5.1 is deprecated: Legacy versions of mkdirp are no longer supported. Please update to mkdirp 1.x. (Note that the API surface has changed to use Promises in 1.x.)
➤ YN0061: │ clone@npm:1.0.2 is deprecated: XSS vulnerability fixed in v1.0.3
➤ YN0061: │ istanbul@npm:0.4.5 is deprecated: This module is no longer maintained, try this instead:
  npm i nyc
Visit https://istanbul.js.org/integrations for other alternatives.
➤ YN0061: │ minimatch@npm:2.0.10 is deprecated: Please update to minimatch 3.0.2 or higher to avoid a RegExp DoS issue
➤ YN0061: │ request@npm:2.75.0 is deprecated: request has been deprecated, see https://github.com/request/request/issues/3142
➤ YN0061: │ core-js@npm:2.4.1 is deprecated: core-js@<3 is no longer maintained and not recommended for usage due to the number of issues. Please, upgrade your dependencies to the actual version of core-js@3.
➤ YN0061: │ node-uuid@npm:1.4.7 is deprecated: Use uuid module instead
➤ YN0061: │ hawk@npm:3.1.3 is deprecated: This module moved to @hapi/hawk. Please make sure to switch over as this distribution is no longer supported and may contain bugs and critical security issues.
➤ YN0061: │ har-validator@npm:2.0.6 is deprecated: this library is no longer supported
➤ YN0061: │ cryptiles@npm:2.0.5 is deprecated: This version has been deprecated in accordance with the hapi support policy (hapi.im/support). Please upgrade to the latest version to get the best features, bug fixes, and security patches. If you are unable to upgrade at this time, paid support is available for older versions (hapi.im/commercial).
➤ YN0061: │ is-my-json-valid@npm:2.14.0 is deprecated: catastrophic backtracking in regexes could potentially lead to REDOS attack, upgrade to 2.17.2 as soon as possible
➤ YN0061: │ hoek@npm:2.16.3 is deprecated: This version has been deprecated in accordance with the hapi support policy (hapi.im/support). Please upgrade to the latest version to get the best features, bug fixes, and security patches. If you are unable to upgrade at this time, paid support is available for older versions (hapi.im/commercial).
➤ YN0061: │ sntp@npm:1.0.9 is deprecated: This module moved to @hapi/sntp. Please make sure to switch over as this distribution is no longer supported and may contain bugs and critical security issues.
➤ YN0061: │ boom@npm:2.10.1 is deprecated: This version has been deprecated in accordance with the hapi support policy (hapi.im/support). Please upgrade to the latest version to get the best features, bug fixes, and security patches. If you are unable to upgrade at this time, paid support is available for older versions (hapi.im/commercial).
➤ YN0061: │ is-buffer@npm:1.1.4 is deprecated: This version of 'is-buffer' is out-of-date. You must update to v1.1.6 or newer
➤ YN0000: └ Completed in 3.04s
➤ YN0000: ┌ Fetch step
➤ YN0013: │ xtend@npm:4.0.1 can't be found in the cache and will be fetched from the remote registry
➤ YN0013: │ y18n@npm:3.2.1 can't be found in the cache and will be fetched from the remote registry
➤ YN0013: │ yargs-parser@npm:3.2.0 can't be found in the cache and will be fetched from the remote registry
➤ YN0013: │ yargs@npm:3.10.0 can't be found in the cache and will be fetched from the remote registry
➤ YN0013: │ yargs@npm:5.0.0 can't be found in the cache and will be fetched from the remote registry
➤ YN0000: └ Completed in 10.43s
➤ YN0000: ┌ Link step
➤ YN0000: └ Completed in 0.45s
➤ YN0000: Done with warnings in 13.97s


ζ ls -lart                                                                                                                                                                                                                         [0b8f43f]
total 1600
drwxr-xr-x   3 kiran  project      96  7 Sep 11:55 ..
-rw-r--r--   1 kiran  project      14  7 Sep 11:55 .gitignore
-rw-r--r--   1 kiran  project    1346  7 Sep 11:55 LICENSE
-rw-r--r--   1 kiran  project    2080  7 Sep 11:55 README.md
drwxr-xr-x   3 kiran  project      96  7 Sep 11:55 __tests__
-rw-r--r--   1 kiran  project     253  7 Sep 11:55 index.js
-rw-r--r--   1 kiran  project     485  7 Sep 11:55 package.json
-rw-r--r--   1 kiran  project      40  7 Sep 11:57 .yarnrc.yml
-rw-r--r--   1 kiran  project  108777  7 Sep 11:58 yarn.lock
drwxr-xr-x   6 kiran  project     192  7 Sep 11:58 .yarn
drwxr-xr-x  13 kiran  project     416  7 Sep 11:58 .
-rwxr-xr-x   1 kiran  project  680429  7 Sep 11:58 .pnp.js
drwxr-xr-x  12 kiran  project     384  7 Sep 11:58 .git

ζ wc -l .pnp.js                                                                                                                                                                                                  
   14115 .pnp.js

ζ gs                                                                                                                                                                                                            
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   yarn.lock

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	.pnp.js
	.yarn/
	.yarnrc.yml
```