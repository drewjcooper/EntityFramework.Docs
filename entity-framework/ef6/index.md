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

Entity Framework 6 (EF6) is a tried and tested Object/Relational Mapper (O/RM) with many years of features and stabilization. EF6 enables developers to work with relational data using strongly-typed .NET objects, taking advantage of Language INtegrated Query (LINQ) and services such as automatic change tracking, identity resolution and lazy loading, which eliminate the need for most of the data access code that they usually need to write, and allows them to focus on their application's business logic.

## High-level capabilities   

- Entity Framework works with a variety of database servers (including Microsoft SQL Server, Oracle, and DB2)  
- Includes a rich mapping engine that can handle a wide variety of database schemas and works well with stored procedures  
- Provides integrated Visual Studio tools to visually create entity models and to auto-generate models from an existing database. New databases can be deployed from a model, which can also be hand-edited for full control  
- Provides a Code First experience to create entity models using code. Code First can map to an existing database or generate a database from the model.  
- Integrates well into all the .NET application programming models including ASP.NET.

Entity Framework is built on the existing ADO.NET provider model, with existing providers being updated additively to support the new Entity Framework functionality. Because of this, existing applications built on ADO.NET can be carried forward to Entity Framework easily with a programming model that is familiar to ADO.NET developers.  

## Benefits

Using Entity Framework to write data-oriented applications provides the following benefits:  

- Reduced development time: the framework provides the core data access capabilities so developers can concentrate on application logic.  
- Developers can work in terms of a more application-centric object model, including types with inheritance, complex members, and relationships. From Entity Framework 4, it also supports Persistence Ignorance through Plain Old CLR Objects (POCO) entities.  
- Applications are freed from hard-coded dependencies on a particular data engine or storage schema by supporting a conceptual model that is independent of the physical/storage model.  
- Mappings between the object model and the storage-specific schema can change without changing the application code.  
- Language-Integrated Query support (called LINQ to Entities) provides IntelliSense and compile-time syntax validation for writing queries against a conceptual model.

## About this documentation and past versions of EF

The first version of Entity Framework was released in 2008, as part of .NET Framework 3.5 SP1 and Visual Studio 2008 SP1. Starting with the EF4.1 release it has shipped as the [EntityFramework NuGet package](https://www.nuget.org/packages/EntityFramework/) - currently one of the most popular packages on NuGet.org.

This documentation provides information on Entity Framework 6 (EF6), the latest major version of EF. Although much of it should also apply to past versions, namespaces are different and capabilities may have evolved.

For more information, see [Past Versions of EF](ef6/past-versions-of-entity-framework.md).
