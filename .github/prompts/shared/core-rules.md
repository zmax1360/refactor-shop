# Core Engineering Rules

* Preserve existing behavior unless explicitly requested
* Prefer the smallest safe functional diff possible
* Do not modify unrelated files
* Avoid formatting-only changes
* Do not introduce unnecessary abstractions
* Reuse existing utilities and patterns before creating new ones
* Keep public APIs backward compatible unless explicitly approved

# Spring Boot / Reactive Rules

* Never introduce `.block()` in reactive chains
* Prefer constructor injection over field injection
* Avoid blocking I/O in reactive flows
* Do not use Optional.get() without presence checks
* Use specific exceptions instead of generic RuntimeException
* Extract magic strings to static final constants
* Use @Slf4j annotation, not manual Logger declaration

# Testing Rules

* All code changes must include appropriate tests
* Tests should validate behavior, not implementation details
* Do not use @Disabled without a ticket reference
* Preserve existing test behavior unless fixing broken tests


# Safety Rules

* Never hardcode secrets or credentials
* Do not bypass validation or authorization logic
* Flag breaking changes explicitly
* Stop and report if requirements are ambiguous
* Never suppress warnings or errors without justification
* Do not silently change business logic

# Refactoring Rules

* Refactor only within the requested scope
* Do not rewrite working code without justification
* Minimize risk over architectural perfection
* Prefer incremental improvements over large rewrites
* Preserve existing naming and architectural conventions unless inconsistent or harmful

# Verification Rules

* Never report compile/test PASS unless the command was actually executed successfully
* Include real command output for failures
* If verification was not executed, explicitly state:
  "Verification not executed"
* Do not assume build success from static analysis alone

# Compression Rules

* Do not restate previously known requirements
* Reference IDs instead of repeating full descriptions
* Keep handoffs under 5 bullet points
* Avoid repeating state already present in the state file
* Prefer concise summaries over large tables
* Compress completed sections where possible

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

