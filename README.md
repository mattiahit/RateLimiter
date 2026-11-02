# Dynamic Rate Limiter & Throttling Spring Boot Starter

A lightweight, reusable **Spring Boot Starter** designed to protect REST controllers and core service methods from resource exhaustion, brute-force attacks, and API quota breaches using Aspect-Oriented Programming (AOP).

---

## Key Features

* **Annotation-driven:** Easily apply `@RateLimited` to any method or controller endpoint.
* **Flexible Execution Scope:** Works seamlessly on both Web/HTTP layers (resolving Client IP/JWT context) and internal Service components.
* **Spring Boot Auto-configuration:** Zero-boilerplate setup. Integrates automatically when added as a dependency.
* **Extensible Architecture:** Pluggable `RateLimiter` storage engine (defaults to an in-memory Token Bucket with thread-safe `ConcurrentHashMap`; easily replaceable with Redis/Bucket4j).
* **Conditional Enablement:** Toggle feature on or off via standard Spring Boot configuration properties.

---

## Architectural Overview

The starter intercepts annotated method executions before they reach the underlying business logic, determining whether to allow execution or reject it with a rate limit exception: