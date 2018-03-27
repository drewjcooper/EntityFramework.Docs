---
title: "Entity Framework Version History - EF6"
author: divega
ms.date: "2016-10-23"
ms.prod: "entity-framework"
ms.author: divega
ms.manager: avickers


ms.technology: entity-framework-6
ms.topic: "article"
ms.assetid: 41d1f86b-ce66-4bf2-8963-48514406fb4c
caps.latest.revision: 3
---
# Entity Framework Version History

Here is a summary of the Entity Framework releases and the features they added.

## Future Versions

While most of the focus of the EF team is nowadays on adding new features and improvements to [EF Core](https://docs.microsoft.com/en-us/ef/core/index), we plan to keep fixing important bugs, implementing small improvements, and incorporating community contributions in the EF6 codebase.

The roadmap of post-EF 6.2 releases is currently being developed. More information will be posted here once available on the [.NET team blog](https://blogs.msdn.microsoft.com/dotnet/tag/entity-framework/) or [Twitter](http://twitter.com/efmagicunicorns).

### EF 6.2 Tools

We plan to release an updated version of the EF6 tooling in Visual Studio 2017. It will include improvements on the top pain points:

- Accessibility overhaul
- Workaround for SQL Server performance regression on reverse engineering [#4](https://github.com/aspnet/entityframework6/issues/4)
- Update model from database support for larger models on SQL Server [#185](https://github.com/aspnet/EntityFramework6/issues/185)

## Recent releases

### EF 6.2

To a great extent thanks to the efforts our community of open source contributors, EF 6.2 includes numerous [bugs fixes](https://github.com/aspnet/entityframework6/issues?utf8=%E2%9C%93&q=is%3Aissue%20milestone%3A6.2.0%20is%3Aclosed%20label%3Aclosed-fixed%20-label%3Aarea-tools%20label%3Atype-bug) and [product enhancements](https://github.com/aspnet/entityframework6/issues?utf8=%E2%9C%93&q=is%3Aissue%20milestone%3A6.2.0%20is%3Aclosed%20label%3Aclosed-fixed%20-label%3Aarea-tools%20label%3Atype-enhancement%20).

Here is a brief list of the most important changes affecting the runtime:

- Reduce start up time by loading finished code first models from a persistent cache [#275](https://github.com/aspnet/EntityFramework6/issues/275)
- Fluent API to define indexes [#274](https://github.com/aspnet/EntityFramework6/issues/274)
- DbFunctions.Like() to enable writing LINQ queries that translate to LIKE in SQL [#241](https://github.com/aspnet/EntityFramework6/issues/241)
- Migrate.exe should support -script option [#240](https://github.com/aspnet/EntityFramework6/issues/240)
- EF6 does not work with primary key from sequence [#165](https://github.com/aspnet/EntityFramework6/issues/165)
- Update error numbers for SQL Azure Execution Strategy [#83](https://github.com/aspnet/EntityFramework6/issues/83)
- Bug: Retrying queries or SQL commands fails with "The SqlParameter is already contained by another SqlParameterCollection" [#81](https://github.com/aspnet/EntityFramework6/issues/81)
- Bug: Evaluation of DbQuery.ToString() frequently times out in the debugger [#73](https://github.com/aspnet/EntityFramework6/issues/73)

## Past releases

### EF 6.1.2
This version is mostly about bug fixes. We also accepted a couple of noteworthy changes from members of the community:
- **Query cache parameters can be configured from the app/web.configuration file**
    ``` xml
    <entityFramework>
      <queryCache size='1000' cleaningIntervalInSeconds='-1'/>
    </entityFramework>
    ```
- **SqlFile and SqlResource methods on DbMigration** allow you to run a SQL script stored as a file or embedded resource.

### EF 6.1.1
This version contains fixes for issues that a number of people have encountered
- Designer: Error opening EF5 edmx with decimal precision in EF6 designer
- Default instance detection logic for LocalDB doesn't work with SQL Server 2014

### EF 6.1
This minor release adds the following features to EF6:
- **Tooling consolidation** provides a consistent way to create a new EF model. This feature [extends the ADO.NET Entity Data Model wizard to support creating Code First models](../ef6/entity-framework-code-first-to-an-existing-database.md), including reverse engineering from an existing database. These features were previously available in Beta quality in the EF Power Tools.
- **[Handling of transaction commit failures](../ef6/entity-framework-handling-of-transaction-commit-failures-ef6-1-onwards.md)** provides the [CommitFailureHandler](https://msdn.microsoft.com/library/system.data.entity.infrastructure.commitfailurehandler.aspx) which makes use of the newly introduced ability to intercept transaction operations. The CommitFailureHandler allows automatic recovery from connection failures whilst committing a transaction.
- **[IndexAttribute](../ef6/entity-framework-code-first-data-annotations.md)** allows indexes to be specified by placing an [Index] attribute on a property (or properties) in your Code First model. Code First will then create a corresponding index in the database.
- **The public mapping API** provides access to the information EF has on how properties and types are mapped to columns and tables in the database. In past releases this API was internal.
- **[Ability to configure interceptors via the App/Web.config file](../ef6/entity-framework-config-file-settings.md)** allows interceptors to be added without recompiling the application.
- **System.Data.Entity.Infrastructure.Interception.DatabaseLogger**is a new interceptor that makes it easy to log all database operations to a file. In combination with the previous feature, this allows you to easily [switch on logging of database operations for a deployed application](../ef6/entity-framework-config-file-settings.md), without the need to recompile.
- **Migrations model change detection** has been improved so that scaffolded migrations are more accurate; performance of the change detection process has also been enhanced.
- **Performance improvements** including reduced database operations during initialization, optimizations for null equality comparison in LINQ queries, faster view generation (model creation) in more scenarios, and more efficient materialization of tracked entities with multiple associations.

### EF 6.0.2
This patch release is limited to fixing issues that were introduced in the EF6 release (regressions in performance/behavior since EF5).

### EF 6.0.1
This patch release is limited to fixing issues that were introduced in the EF6 release (regressions in performance/behavior since EF5). The most notable changes were to fix some performance issues during warm-up for EF models. This was important as warm-up performance was an area of focus in EF6 and these issues were negating some of the performance gains made in EF6.

### EF 6.0
The EF6 runtime can be installed from NuGet. See the [Get Entity Framework](../ef6/get-entity-framework.md) page for more information.

The following features work for models created with Code First or the EF Designer:

- **[Async Query and Save](../ef6/entity-framework-async-query-and-save-ef6-onwards.md)** adds support for the task-based asynchronous patterns that were introduced in .NET 4.5.
- **[Connection Resiliency](../ef6/entity-framework-connection-resiliency-and-retry-logic-ef6-onwards.md)** enables automatic recovery from transient connection failures.
- **[Code-Based Configuration](../ef6/entity-framework-code-based-configuration-ef6-onwards.md)** gives you the option of performing configuration – that was traditionally performed in a config file – in code.
- **[Dependency Resolution](../ef6/entity-framework-idbdependencyresolver-services-ef6-onwards.md)** introduces support for the Service Locator pattern and we've factored out some pieces of functionality that can be replaced with custom implementations.
- **[Interception/SQL logging](../ef6/entity-framework-logging-and-intercepting-database-operations-ef6-onwards.md)** provides low-level building blocks for interception of EF operations with simple SQL logging built on top.
- **Testability improvements** make it easier to create test doubles for DbContext and DbSet when [using a mocking framework](http://msdn.com/data/dn314429) or [writing your own test doubles](http://msdn.com/data/dn314431).
- **[DbContext can now be created with a DbConnection that is already opened](../ef6/entity-framework-connection-management.md)** which enables scenarios where it would be helpful if the connection could be open when creating the context (such as sharing a connection between components where you can not guarantee the state of the connection).
- **[Improved Transaction Support](../ef6/entity-framework-working-with-transactions-ef6-onwards.md)** provides support for a transaction external to the framework as well as improved ways of creating a transaction within the Framework.
- **Enums, Spatial and Better Performance on .NET 4.0** - By moving the core components that used to be in the .NET Framework into the EF NuGet package we are now able to offer enum support, spatial data types and the performance improvements from EF5 on .NET 4.0.
- **Improved performance of Enumerable.Contains in LINQ queries**.
- **Improved warm up time (view generation)**, especially for large models.
- **Pluggable Pluralization &amp; Singularization Service**.
- **Custom implementations of Equals or GetHashCode** on entity classes are now supported.
- **DbSet.AddRange/RemoveRange** provides an optimized way to add or remove multiple entities from a set.
- **DbChangeTracker.HasChanges** provides an easy and efficient way to see if there are any pending changes to be saved to the database.
- **SqlCeFunctions** provides a SQL Compact equivalent to the [SqlFunctions](https://msdn.microsoft.com/library/system.data.objects.sqlclient.sqlfunctions.aspx).

The following features apply to Code First only:

- **[Custom Code First Conventions](../ef6/entity-framework-custom-code-first-conventions-ef6-onwards.md)** allow write your own conventions to help avoid repetitive configuration. We provide a simple API for lightweight conventions as well as some more complex building blocks to allow you to author more complicated conventions.
- **[Code First Mapping to Insert/Update/Delete Stored Procedures](../ef6/entity-framework-code-first-insert-update-and-delete-stored-procedures.md)** is now supported.
- **[Idempotent migrations scripts](../ef6/entity-framework-code-first-migrations.md)** allow you to generate a SQL script that can upgrade a database at any version up to the latest version.
- **[Configurable Migrations History Table](../ef6/entity-framework-customizing-the-migrations-history-table-ef6-onwards.md)** allows you to customize the definition of the migrations history table. This is particularly useful for database providers that require the appropriate data types etc. to be specified for the Migrations History table to work correctly.
- **Multiple Contexts per Database** removes the previous limitation of one Code First model per database when using Migrations or when Code First automatically created the database for you.
- **[DbModelBuilder.HasDefaultSchema](../ef6/entity-framework-fluent-api-configuring-and-mapping-properties-and-types.md)** is a new Code First API that allows the default database schema for a Code First model to be configured in one place. Previously the Code First default schema was hard-coded to &quot;dbo&quot; and the only way to configure the schema to which a table belonged was via the ToTable API.
- **DbModelBuilder.Configurations.AddFromAssembly method** allows you to easily add all configuration classes defined in an assembly when you are using configuration classes with the Code First Fluent API.
- **[Custom Migrations Operations](http://romiller.com/2013/02/27/ef6-writing-your-own-code-first-migration-operations/)** enabled you to add additional operations to be used in your code-based migrations.
- **Default transaction isolation level is changed to READ_COMMITTED_SNAPSHOT** for databases created using Code First, allowing for more scalability and fewer deadlocks.
- **Entity and complex types can now be nestedinside classes**. |

### EF 5.0
This release introduces some new features including enum support, table-valued functions, spatial data types and various performance improvements.

The Entity Framework Designer in Visual Studio 2012 also introduces support for multiple-diagrams per model, coloring of shapes on the design surface and batch import of stored procedures.

### EF 4.3.1
This patch release included some bug fixes to the EF 4.3 release and introduced better LocalDb support for folks using EF 4.3 with Visual Studio 2012.

### EF 4.3
The EF 4.3 release included the new Code First Migrations feature that allows a database created by Code First to be incrementally changed as your Code First model evolves.

### EF 4.2

This release includes bug fixes to the EF 4.1.1 release. Because this release only included bug fixes it could have been the EF 4.1.2 patch release but we opted to move to 4.2 to allow us to move away from the date based patch version numbers we used in the 4.1.x releases and adopt the [http://semver.org](http://semver.org) standard for semantic versioning.

### EF 4.1.1
In addition to bug fixes this patch release introduced some components to make it easier for design time tooling to work with a Code First model. These components are used by Code First Migrations (included in EF 4.3) and the EF Power Tools.

Note the NuGet package for this release has the version number 4.1.10715. We used to use date based patch versions before we decided to adopt the [http://semver.org](http://semver.org) standard for semantic versioning.

### EF 4.1
The EF 4.1 release was the first to be published on NuGet. This release included the simplified DbContext API and the Code First workflow.

Note the NuGet package for this release has the version number 4.1.10331. We used to use date based patch versions before we decided to adopt the [http://semver.org](http://semver.org) standard for semantic versioning.

### EF 4.0
This release was included in .NET Framework 4 and Visual Studio 2010. New features in this release included POCO support, lazy loading, testability improvements, customizable code generation and the Model First workflow.

Although it was the second release of Entity Framework it was named EF 4 to align with the .NET Framework version that it shipped with. After this release we started making Entity Framework available on NuGet and adopted semantic versioning since we were no longer tied to the .NET Framework Version.

### EF 3.5
The initial release of Entity Framework was included in .NET 3.5 SP1 and Visual Studio 2008 SP1. This release provided basic O/RM support using the Database First workflow.
