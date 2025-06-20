<p align="center">
  <img src="images/logo.webp" alt="Water Framework Logo" width="200"/>
</p>

# Water Framework - be water my friend ;)
 *"Empty your mind, be formless. Shapeless, like water. If you put water into a cup, it becomes the cup. You put water into a bottle and it becomes the bottle. You put it in a teapot, it becomes the teapot. Now, water can flow or it can crash. Be water, my friend."* - Bruce Lee

## Summary
1. [What is Water Framework](#introduction)
    1. [First Pillar]()
    2. [Second Pillar]()
    3. [Third Pillar]()
2. [Founding Principles](#principles)
3. [Getting Started](#getting-started)
4. [Core Concepts](#core-concepts)

##  What is Water Framework ? <a name="introduction"></a>

![Water Framework Concepts](images/water-framework-concepts-v2.png)

Water framework is a "cross-framework" that is, it allows you to write modular applications that can run on different java runtimes (for the time being) such as spring,osgi, quarkus, etc...

The key feature of Water Framework is that it takes the form of the container that incorporates it (like water, precisely).

What are the main advantages of this framework? First of all it has a number of "out of the box" features such as:

* User management
* Granular permission system
* Integrations with different technologies
* Integrations for realtime/event streaming applications. 

In addition, all these features are customizable. Do you have needs to change the permission system to your liking and totally and/or partially override the default behavior? No problem! Water Framework has a 100% modular structure based on SOLID principles of object-oriented programming.
It was created to support all the latest technologies and defines a new "Convention over coding" development standard.

This means that the structure of applications follows certain mechanisms and dynamics that allows them to have truly simple code management (from development to build and deployment) and interface remoting.
"Convention over coding" is not just a "development to a standard" but a set of techniques, tools and code conventions that ,if followed, drastically cut down development time and especially code maintenance.

The way it is described, our solution sounds very similar to the classic "Convention over configuration." In reality, it is not.
The so-called "Convention over configuration" reduces the configurations to be specified by the developer who can rely on some "default" conventions of the technology used.

One example out of all: @Entity on a Java class will associate a table with the class name if not specified.
This type of approach is certainly useful and is currently used within the framework, but we have decided to go even further.

You might think that all these advantages require special libraries or constructs where you lose control of the code. They don't. Water Framework is extremely clear and has very simple concepts that do not complicate but rather help you structure your source code better.
In fact, you can design monolithic or microservices applications, or the classic "modulith" or hybrid of microservices and monoliths.

Water Framework three main pillars are:

* Water Framework
* Tools (Water Framework Generator)
* Runtimes

### First Pillar: Water Framework

As mentioned earlier, the framework has a whole set of "out of the box" features that allow applications to be created quickly and already provided with a basic infrastructure (user management, permissions, event streaming integrations). Project creation can also be managed through "water-generator" the code generator that helps scaffolding projects quickly.
It is possible to create complex applications that manage permissions, accesses, entities and expose rest services in minutes.
The most interesting thing about Water Framework is that the developer can choose whether he wants to develop his application for a specific runtime (spring, osgi, quarkus) or whether he wants to develop his application in "cross-framework" mode so that it too can be enjoyed by different runtimes as needed.

### Second Pillar: Water Framework Generator

The generator allows automating the project creation process, including the selection of technology. Additionally, it is possible to scaffold modules that are "cross-framework," enabling the creation of traditional applications for a specific runtime or applications that support different runtimes.
In the perspective of managing complex applications, the generator also performs dependency analysis, potentially identifying cycles. Cycles in project dependencies are one of the main obstacles to proper design, and discovering them usually happens late, typically when new versions are released.
During each build, the generator verifies the integrity of dependencies, triggering errors in the case of circular dependencies.
Finally, it also provides insights into the quality of the produced software through stability metrics.
The stability metrics indicate the quality of the code according to a very simple principle:

Modules containing abstractions should have a high degree of import (i.e., be imported by other projects).
Modules containing implementations should not have a high degree of import precisely because they are subject to change.
The generator calculates the degree of abstraction for each module and provides a measure (along with an index of the results) to determine whether the design is appropriate or not.

### Third Pillar: Runtimes

With Water Framework you can choose to:

- Develop an application in your reference java technology already taking advantage of all the out of the box features with the constructs specific to your technology. E.g. if you use spring all components will be registered as spring beans and will have the classic behavior that every spring developer expects. 
  If you use OSGi you will find the out of the box features as Declarative Services OSGi. Basically you can use Water Framework as a facilitator to increase your productivity by taking advantage of some of the features already provided.

- Develop a cross-framework application. By taking advantage of simple annotations such as @FrameworkComponent you can write an application that can run on both Spring,OSGi and Quarkus and, if you want, in Standalone mode as well.

This feature makes applications customizable because each team can write code with the technology they are most comfortable with. In addition, the generator will make you super productive by already creating a solid base infrastructure.

### Who should use it?

All developers who are building a product that allows them to be able to integrate their own modules within the main solution.
Whether it is a library or an extensible water platform would allow it to be enjoyed and customized by leveraging the framework that is "most convenient" for those who have to write the customizations.

Suppose we wrote a CMS with water framework and suppose we allow the user to be able to write their own modules. Water would allow you to be able to start the CMS in "spring," and the user could write their customizations directly using spring.
Another user might decide instead to svrivere customizations in Quarkus because they are using it in this version.
Finally, a user who wants to write modules that in turn are "cross-framework" can safely do so by using just water framework in his modules.
So using this solution allows you to be able to write libraries and/or applications that can then be customized with whatever technology you want. This is particularly convenient in some business contexts where there are specific policies about what framework or technologies to use. Some companies use only OSGi, others only spring, and so on.

With Water, every module written can be enjoyed natively on the major Java frameworks on the market.

### Architecture

![Water Ark](images/water-high-ark.png)

The basic components of the architecture are the following:

- Core:
- Repository:
- Jpa Repository:
- Rest: 

#### Core

The Core module is the foundation of the Water Framework, providing essential services and abstractions:

- **Security & Permissions**: Implements a granular permission system with role-based access control
- **Service Registry**: Manages component registration and dependency injection across different runtimes
- **Event System**: Provides a robust event handling mechanism for real-time applications
- **Validation**: Offers a flexible validation framework for data integrity
- **Interceptors**: Supports AOP-like functionality for cross-cutting concerns

Key features:
- 100% modular design
- Runtime-agnostic implementations
- Extensible security model
- Built-in event streaming support
- Comprehensive test coverage

#### Repository

The Repository module provides a unified data access layer:

- **Generic Repository Pattern**: Abstracts data access operations
- **Query Builder**: Type-safe query construction
- **Pagination Support**: Built-in pagination and sorting
- **Filter System**: Flexible filtering capabilities
- **Transaction Management**: Cross-runtime transaction support

#### JPA Repository

Extends the Repository module with JPA-specific implementations:

- **JPA Integration**: Seamless integration with JPA providers
- **Entity Management**: Enhanced entity lifecycle management
- **Query Optimization**: Advanced query optimization features
- **Caching**: Multi-level caching support
- **Audit Trail**: Automatic audit trail generation

#### Rest

The Rest module provides RESTful API capabilities:

- **Resource Mapping**: Automatic REST resource mapping
- **Content Negotiation**: Flexible content type handling
- **Security Integration**: Built-in security filters
- **Documentation**: Automatic API documentation
- **Versioning**: API versioning support

##  Getting Started <a name="getting-started"></a>

To get started with Water Framework:

1. Install prerequisites:
   - Java 17 or higher
   - Node.js 18.20.8 or higher
   - Gradle 7.6 or higher

2. Install the Water Generator:
   ```bash
   npm install -g yo generator-water --registry https://nexus.acsoftware.it/nexus/repository/npm-acs-public-repo
   ```

3. Create a new project:
   ```bash
   yo water:app
   ```

4. Follow the interactive prompts to:
   - Choose your target runtime
   - Select required features
   - Configure project settings

##  Core Concepts <a name="core-concepts"></a>

### Framework Components

- **@FrameworkComponent**: Marks a class as a framework component
- **@Service**: Defines a service component
- **@Repository**: Marks a data access component
- **@Security**: Defines security constraints

### Security Model

- Role-based access control
- Permission-based authorization
- Resource-level security
- Cross-runtime security context

### Event System

- Event publishing and subscription
- Asynchronous event processing
- Event filtering and routing
- Cross-runtime event propagation

### Repository Pattern

- Generic CRUD operations
- Type-safe queries
- Pagination and sorting
- Filter system
- Transaction management

### REST API

- Resource mapping
- Content negotiation
- Security integration
- API versioning
- Documentation generation








