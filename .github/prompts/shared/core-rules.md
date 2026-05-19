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
* Distinguish between:
  * targeted task verification
  * full repository verification
* Explicitly classify whether failures are:
  * pre-existing
  * environment-related
  * introduced by the current changes



