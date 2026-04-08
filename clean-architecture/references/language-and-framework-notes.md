# Language And Framework Notes

## Java And Kotlin

- Keep Spring/Micronaut annotations out of domain layer.
- Use interfaces for ports and adapter implementations in infrastructure modules.
- Enforce package-level dependency rules with architecture tests.

## C#

- Keep ASP.NET controllers as adapters only.
- Place use cases in application layer with explicit interfaces.
- Keep EF Core entities and mappings outside domain policies.

## Go

- Use packages to model boundaries clearly.
- Keep interfaces small and located near consumers in policy layers.
- Keep framework/router and storage concerns in outer packages.

## Python

- Keep FastAPI/Django concerns out of use case modules.
- Use protocol or abstract interfaces for ports.
- Keep pydantic/ORM models at boundaries with explicit mapping.

## JavaScript And TypeScript

- Keep framework code (Express/Nest/Next) in adapter layers.
- Define input/output contracts independent of transport objects.
- Keep business policies independent from ORM and HTTP libraries.
