---
title: Entity Framework 6 Quick Overview
author: divega
ms.date: "2016-10-23"
ms.prod: "entity-framework"
ms.author: divega
ms.manager: avickers
ms.technology: entity-framework-6
ms.topic: "article"
ms.assetid: 8ae74d63-6bad-4686-b325-bbf9d68f3743
caps.latest.revision: 5
uid: ef6/index
---
# Entity Framework 6 Quick Overview

Entity Framework 6 (EF6) is a tried and tested Object/Relational Mapper (O/RM) with many years of features and stabilization. EF6 enables developers to work with relational data using strongly-typed .NET objects, taking advantage of Language INtegrated Query (LINQ) and services such as automatic change tracking, identity resolution and lazy loading. EF6 eliminates the need for most of the data access "plumbing" code that they usually need to write, and allows them to focus on their application's business logic.

## Should I use EF6 or EF Core?

EF Core is a more modern, lightweight and extensible version of Entity Framework. EF Core is a complete rewrite and contains many new features not available in EF6, although it also still lacks some of the most advanced mapping capabilities of EF6. We recommend using EF Core in new applications as long as the feature set matches your requirements. See the section [Compare EF Core & EF6](xref:efcore-and-ef6/index) for a detailed explanation of this choice.

The following sections are not intended as a comparison between EF6 and EF Core, but as an explanation of general capabilities and benefits of using EF6.

## High-level capabilities of EF6   

- Entity Framework works with a variety of database servers (including SQL Server, Oracle, and DB2)  
- Includes a rich mapping engine that can handle a wide variety of database schemas and works well with stored procedures  
- Provides integrated Visual Studio tools to visually create entity models and to auto-generate models from an existing database. New databases can be deployed from a model, which can also be hand-edited for full control  
- Provides a Code First experience to create entity models using code. Code First can map to an existing database or generate a database from the model.  
- Integrates well into all the .NET Framework application programming models including ASP.NET.
- Entity Framework builds on the ADO.NET provider model, and takes advantage of existing ADO.NET providers, although Entity Framework providers are required to support the new Entity Framework functionality.

## Benefits of EF6

Using Entity Framework to write data-oriented applications provides the following benefits compared to not using an Object/Relational Mapper:  

- Reduced development time: the framework provides the core data access capabilities so developers can concentrate on application logic.  
- Developers can work in terms of a more application-centric object model, including types with inheritance, complex members, and relationships. From Entity Framework 4, it also supports Persistence Ignorance through Plain Old CLR Objects (POCO) entities.  
- Applications are freed from hard-coded dependencies on a particular data engine or storage schema by supporting a conceptual model that is independent of the physical/storage model.  
- Mappings between the object model and the storage-specific schema can change without changing the application code.  
- Language-Integrated Query support (called LINQ to Entities) provides IntelliSense and compile-time syntax validation for writing queries against a conceptual model.

## About past versions of EF

The first version of Entity Framework was released in 2008, as part of .NET Framework 3.5 SP1 and Visual Studio 2008 SP1. Starting with the EF4.1 release it has shipped as the [EntityFramework NuGet Package](https://www.nuget.org/packages/EntityFramework/) - currently one of the most popular packages on NuGet.org.

This documentation provides information on Entity Framework 6 (EF6), the latest major version of EF. Although much of it should also apply to past versions, namespaces are different and capabilities may have evolved.

For more information, see [Entity Framework Version History](~/ef6/versions/entity-framework-version-history.md).
