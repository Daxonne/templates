# Changelog

All notable changes to this repository will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [Unreleased]

---

## [1.0.0] — 2026-03-02

### Added

#### Registry
- `registry.json` — machine-readable list of all available templates, fetched at runtime by `daxonne add --list`

#### Template — `csharp-dapper` (v1.0.0)
- `{{PascalCase name}}Dto.cs` — C# immutable `record` with one correctly typed property per column
- `{{PascalCase name}}Repository.cs` — Dapper repository with `GetAllAsync`, `GetByIdAsync`, `InsertAsync`, `DeleteAsync`
- Supports nullable properties (`string?`, `int?`, …) based on column nullability

#### Template — `typescript-prisma` (v1.0.0)
- `{{PascalCase name}}.ts` — TypeScript `interface` with optional properties for nullable columns
- `{{PascalCase name}}Service.ts` — Prisma client service with `getAll`, `getById`, `create`, `delete`
- Uses `TypeScriptType` helper for correct type mapping (`number`, `boolean`, `Date`, `Uint8Array`, …)

#### Template — `java-jpa` (v1.0.0)
- `{{PascalCase name}}.java` — Jakarta EE `@Entity` class with `@Table`, `@Column`, `@Id`, `@GeneratedValue` annotations and getters/setters
- `{{PascalCase name}}Repository.java` — Spring Data `JpaRepository` interface
- Uses `JavaType` helper (`String`, `Integer`, `Long`, `BigDecimal`, `LocalDate`, `LocalDateTime`, `UUID`, …)

#### Template — `python-sqlalchemy` (v1.0.0)
- `{{SnakeCase name}}.py` — SQLAlchemy declarative model with `Column` definitions and `__repr__`
- `{{SnakeCase name}}_repository.py` — async repository using `AsyncSession` with `get_all`, `get_by_id`, `insert`, `delete`
- Uses `SQLAlchemyType` helper (`String`, `Integer`, `BigInteger`, `Numeric`, `Boolean`, `Date`, `DateTime`, `LargeBinary`, `Uuid`)

[Unreleased]: https://github.com/Daxonne/templates/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/Daxonne/templates/releases/tag/v1.0.0
