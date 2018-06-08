# lerna-independent

knex js, bookshelf js, lerna js

LERNA : https://github.com/reggi/lerna-tutorial
LERNA
	- lerna is a tool that allows you to maintain multiple npm packages within one repository.
	- keeps all modules in one git repository
	- shared metadata & config at the root
	- each module remains independent
	
	- Single lint, build, test and release process.
	- Easy to coordinate changes across modules.
	- Single place to report issues.
	- Easier to setup a development environment.
	- Tests across modules are ran together which finds bugs that touch multiple modules easier.
	
lerna bootstrap
	- links dependencies in the repo together
	- installs external dependencies
	- symlinks internal dependencies
	
lerna updated
	- list which packages have changed since last release
	
lerna run/exec
	- run npm script in some or all modules
	- execute arbitary command in some or all modules
	
lerna publish
	- publish pakages in current Lerna Project
	- update the version updated packages
	- update all the dependencies of the updated packages with the new versions
	- commit and tag the new version
	- publish updated packages to npm
	
lerna ls
	- list all the public packages in the repo
	
lerna links
	- symlink together all packages that are dependencies of each other in the current repo
	
lerna import
	- import an existing module including git history
	
lerna clean
	- delete all node_modules folders

	- - - - - - - - - - - - - - - - - - - - - 
	npm init - will create package.json in directory of package folder
	- - - - - - - - - - - - - - - - - - - - - 
	
	
lerna init

	- Fixed/Locked mode (default)
		Fixed mode Lerna projects operate on a single version line. The version is kept in the lerna.json
		Use this if you want to automatically tie all package versions together.
		
	- Independent mode (--independent)
		Independent mode Lerna projects allows maintainers to increment package versions independently of each other.
		Independent mode allows you to more specifically update versions for each package and makes sense for a group of components.
		

lerna init --independent
	OR
lerna init --exact

Create folders in pakage.js
	- e.g.  applie, banana, mango
	
	run "lerna init" in all folders
	
	==> lerna add <package>[@version] [--dev]
	e.g. lerna add sample-package@1.0.0
		it will create node_module, pakage.json in all sub pakages
		
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 

lerna add new-module
	- Install new-module in all modules except module-1

lerna add module-one
	- Install module-one to all modules  except module-1 ( in dependencies )

lerna add module-one --scope=module-two
	- Install module module-one in module module-two ( in dependencies )
	
lerna bootstrap
	* Installs all of their dependencies and links any cross-dependencies.
	- Bootstrap the packages in the current Lerna repo. 
	- When run, this command will:
		- npm install all external dependencies of each package.
		- Symlink together all Lerna packages that are dependencies of each other.
		- npm run prepublish in all bootstrapped packages.
		- npm run prepare in all bootstrapped packages.
		
lerna publish -c
	- create a direct release, get aplha version of current version automatically
	
lerna publish --skip-git
	- will publish to npm without running any of the git commands.
	- Only publish to npm; skip committing, tagging, and pushing git changes (this only affects publish).
	
lerna publish --skip-npm
	- will update all package.json package versions and dependency versions, but it will not actually publish the packages to npm.
	
lerna updated
	- Check which packages have changed since the last release.
	
lerna diff [package?]
	- Diff all packages or a single package since the last release.
	
lerna ls
	- List all of the public packages in the current Lerna repo.
