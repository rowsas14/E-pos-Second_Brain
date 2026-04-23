<!--
meta:
  title: Backend Folder Structure
  owner: Backend Engineering
  status: active
  last_reviewed: 2026-04-22
  tags: [backend, folder-structure, clean-architecture, modules]
-->

# Backend Folder Structure

## Purpose

This file defines how the backend codebase should be organized so that:

- Clean Architecture boundaries remain visible
- feature/module ownership stays clear
- requests, DTOs, domain rules, repositories, and responses do not get mixed together
- transaction-sensitive workflows remain maintainable

## Primary structure

The uploaded backend direction shows four main layers:

- **API**
- **Application**
- **Domain**
- **Infrastructure**

It also shows **feature/module-based grouping** inside those layers.

## Example high-level structure

```text
POSSystem/
  POS.API/
    Modules/
      Auth/
      Products/
      Orders/
      Payments/
      Customers/
    Middlewares/
    Filters/
    Extensions/

  POS.Application/
    Modules/
      Products/
      Orders/
      Payments/
      Customers/
      Inventory/
      Auth/
    Common/

  POS.Domain/
    Modules/
      Products/
      Orders/
      Payments/
      Customers/
      Inventory/
    Common/

  POS.Infrastructure/
    Persistence/
    Repositories/
    Services/
    UnitOfWork/
```

The exact module list can grow with the platform, but the **layer separation** and **feature grouping** should stay consistent.

## API layer structure

Use API for HTTP-facing concerns.

```text
POS.API/
  Modules/
    Products/
      Controllers/
      Requests/
      Responses/
```

### API layer should contain

- controllers
- request models
- response models
- route-level filters when needed
- middleware registration and global pipeline configuration
- application registration extensions

### API layer should not contain

- EF Core queries
- direct repository access
- business workflow orchestration
- domain invariants
- transaction coordination logic

## Application layer structure

Use Application for use-case orchestration.

```text
POS.Application/
  Modules/
    Products/
      ProductService.cs
      CreateProductDto.cs
      UpdateProductDto.cs
      ProductResponseDto.cs
      ProductListDto.cs
      ProductValidator.cs
      Interfaces/
        IProductService.cs
        IProductRepository.cs
    Orders/
    Payments/
  Common/
    Interfaces/
      IUnitOfWork.cs
      ICurrentUserContext.cs
    Responses/
      ApiResponse.cs
```

### Application layer should contain

- use-case services
- application interfaces
- action-specific DTOs
- validators
- orchestration logic
- transaction coordination requests through Unit of Work contracts

### Application layer should not contain

- HTTP request/response models
- EF Core implementation details
- controller logic
- infrastructure integration details

## Domain layer structure

```text
POS.Domain/
  Modules/
    Products/
      Product.cs
      ProductCategory.cs
    Orders/
      Order.cs
      OrderItem.cs
      OrderDomainService.cs
  Common/
    BaseEntity.cs
```

### Domain layer should contain

- entities
- aggregates
- value objects
- domain services
- invariant-protecting behavior

## Infrastructure layer structure

```text
POS.Infrastructure/
  Persistence/
    ApplicationDbContext.cs
    Configurations/
    Migrations/
  Repositories/
    Products/
      ProductRepository.cs
    Orders/
    Payments/
  Services/
    PaymentGateway/
    Messaging/
  UnitOfWork/
    UnitOfWork.cs
```

### Infrastructure layer should contain

- EF Core DbContext and configurations
- repository implementations
- integration services
- Unit of Work implementation
- persistence concerns

## Where common contracts should live

| Contract type | Preferred location |
|---|---|
| application service interface | Application module `Interfaces/` |
| repository interface | Application module `Interfaces/` or Application common interfaces |
| Unit of Work contract | Application common interfaces |
| Unit of Work implementation | Infrastructure `UnitOfWork/` |
| API response wrapper | Application common responses or shared contract area |

## DTO, request, and response placement

Keep these separate:

| Type | Location | Example |
|---|---|---|
| API request model | API module `Requests/` | `CreateProductRequest.cs` |
| API response model | API module `Responses/` | `ProductResponse.cs` |
| application DTO | Application module root or contracts area | `CreateProductDto.cs`, `ProductListDto.cs` |
| domain entity | Domain module | `Product.cs` |

Do not collapse these into one model unless the use case genuinely does not require separation.

## Related documents

- [clean-architecture-rules.md](./clean-architecture-rules.md)
- [application-layer-rules.md](./application-layer-rules.md)
- [dto-handling-rules.md](./dto-handling-rules.md)
- [mapping-rules.md](./mapping-rules.md)
- [repository-rules.md](./repository-rules.md)
- [../02-architecture/backend-architecture.md](../02-architecture/backend-architecture.md)
