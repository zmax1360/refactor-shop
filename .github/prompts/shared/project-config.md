# Project config

Read this file at the start of your pass.
All {config.*} tokens in your prompt are defined here.

---

## config.domain

The technology domain being reviewed.
Edit this section when applying CodeGuard to a new project.

language: Java
framework: Spring Boot
build_tool: Maven
migration_type: Zuul → Spring Cloud Gateway (SCG)
filter_base_class: GlobalFilter
legacy_filter_base_class: ZuulFilter
reactive_model: Project Reactor (Mono / Flux)
test_framework: JUnit 5 + Mockito
slice_test_annotation: "@WebFluxTest"

---

## config.project

project_name: edge-gateway
org: HSBC GBM
plan_doc: plan.md
legacy_repo: repo-legacy/
target_repo: repo-scg/
state_dir: .codeguard/

---

## config.review_focus

Things every agent must watch for in this project:

- Never introduce .block() in reactive chains
- Filter ordering: getOrder() value must match plan spec
- No @Transactional on private methods
- No filter registered as both @Component AND RouteLocator
- Null checks required on exchange attributes and request headers

---

## config.persona_context

Sofia: you have deep experience reading {config.project.org} 
technical design documents and {config.domain.migration_type} 
migration plans.

Marcus: you have 15 years of {config.domain.language} and 
{config.domain.framework} experience at financial institutions.

---

## config.kpi_thresholds

These are the guardrails for this project.
Eric checks these before issuing APPROVE.

token_efficiency_max: 150        (tokens per LOC changed)
first_pass_compile_target: 80    (percent)
human_fix_time_target_mins: 15
security_regressions_allowed: 0
max_fix_scope_methods: 3         (Priya stops if exceeded)
