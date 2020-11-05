# Layer2 Interview - .NET Core Assessment

This repository is part of Layer2's hiring process and it was designed to asses a candidate's abilities to implement Domain-Driven Design techniques using .NET Core technologies.

This depository provides a sample .NET solution with a few empty projects where candidates will be adding their implementation following the instructions coming next. As a candidate, please clone this repository and use it as a starting point for your implementation.

## Overview

You will be developing a simple application that helps Layer2 to manage project schedule. You are not required to develop a full application, only a few backend elements described in the technical requirements.

### Problem Scenario

As a growing company Layer2 manages dozens of small concurrent projects. Every project has what we call **Project Schedule** which is used to control when the project starts, when it is expected to finish, and the current completion percentage (0% - 100%).

A typical Project Schedule contains the following elements:

* A list of Milestones
* Start Date
* End Date
* Completion (0% - 100%)

**List of Milestones**

The Project Schedule is calculated based on a list of milestones established by the user. Milestones are major goals to be achieved by the project. Each milestone contains the following elements:

* Name (No more than 256 characters)
* Start Date
* End Date
* Completion (0% - 100%)

Users can add new milestones to a Project Scope, remove milestones from a Project Scope, and they can also change any of the fields of the milestone.

**Start Date**

The start date is automatically calculated based on the milestones - the start date of the earliest milestone will determine the start date the Project Schedule.

If not milestones are present, the Start Date should be blank to indicate that the Project Schedule has not yet been defined.

**End Date**

The end date is automatically calculated based on the milestones - the end date of the last milestone will determine the end date the Project Schedule.

If not milestones are present, the End Date should be blank to indicate that the Project Schedule has not yet been defined.

**Completion**
 
 The completion of the Project Schedule is automatically calculated by taking an average of the completion of each milestone.

## Technical Requirements

You are required to implement a few backend elements that would typically be part of a Web API project:

* Domain entities
* Unit tests
* Data Persistence (Entity Framework Core)

To be successful, your implementation must follow a typical Domain-Driven Design architecture:

https://res.cloudinary.com/practicaldev/image/fetch/s--sWdyI1q4--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/dhti2v0e1smn055tages.png

You are not required to implemented all the components and layers of this architecture. Only the following elements are required to be implemented:
 
 * **Domain Layer**: Entities and Unit Tests
 * **Persistence Layer**: DbContext and Entities Mapping (Using Entity Framework Core)
 
Please make sure your projects use either .NET Core 3.1 or .NET Standard 2.1.

### Domain Layer

#### Entities 
As candidate you are expected to implement rich and testable domain entities that handle all the core business logic. To be successful in this assessment, your domain entities implementation must be guided by Domain-Drive Design techniques such as rich-persistence-ignorant entities, aggregates and value objects.

The sample solution contains a project named **Layer2.Domain**. Please use this project to add the source code for your domain implementation. 

#### Unit Tests
You are also expected to write unit tests to cover as much as possible of the business logic implemented in your domain entities. When implementing your domain entities, you are highly recommended to use a Test-Driven Development approach. 

Please use the project **Layer2.Domain.Tests** to add the source code for your unit tests. Using **xUnit** as testing framework is a requirement.

### Persistence Layer

You are required to implement your persistence layer using Entity Framework Core. You don't need to implement a full persistence layer, only the following elements are required:

* DbContext: With DbSets for each of your entities
* Entities Mapping: To map your entities to the database using EF Core's Fluent API.

Consider PostgreSQL as your database. Please make sure you use version Entity Framework Core 3.1 or higher.


