# Clean-Architecture

https://jasontaylor.dev/clean-architecture-getting-started/
https://codeopinion.com/clean-architecture-example-breakdown/

![image](https://github.com/vishnu01/Clean-Architecture/assets/10369261/f5257539-223d-433a-a376-4982626f8aac)

The project names within src align closely to the layers of the Clean Architecture diagram, the only exception being WebUI, representing the Presentation layer.

**DOMAIN**
The Domain project represents the Domain layer and contains enterprise or domain logic and includes entities, enums, exceptions, interfaces, types and logic specific to the domain layer. **This layer has no dependencies on anything external**.

**APPLICATION**
The Application project represents the Application layer and contains all business logic. This project implements CQRS (Command Query Responsibility Segregation), with each business use case represented by a single command or query. **This layer is dependent on the Domain layer but has no dependencies on any other layer or project**. 

**This layer defines interfaces that are implemented by outside layers**. For example, if the application needs to access a notification service, a new interface would be added to the Application and the implementation would be created within Infrastructure.

**INFRASTRUCTURE**
The Infrastructure project represents the Infrastructure layer and contains classes for accessing external resources such as file systems, web services, SMTP, and so on. 
**These classes should be based on interfaces defined within the Application layer.**

**UI**
The WebUI project represents the Presentation layer. This project is a SPA (single page app) based on Angular 8 and ASP.NET Core. 
**This layer depends on both the Application and Infrastructure layers. Please note the dependency on Infrastructure is only to support dependency injection.**
