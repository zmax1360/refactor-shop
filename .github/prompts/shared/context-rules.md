
# Context Loading Rules

* Read ONLY files relevant to the current task
* Read ONLY unresolved sections of the state file unless deeper context is required
* Avoid re-reading completed workflow sections
* Do not load unrelated release-plan items
* Prefer targeted file inspection over broad repository scanning
* Only load files directly related to the current release-plan task
* Avoid scanning unrelated modules or features
* Prefer targeted file reads over repository-wide searches
* Use release-plan scope to limit context loading