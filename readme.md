LinQ to SQL Builder - small .NET library supports creating SQL queries and commands in a strongly typed fashion.
---------------------------------------------------------------------------

[![GitHub release](https://img.shields.io/github/v/release/dotnetbrightener/linq-to-sql-builder.svg)](https://GitHub.com/dotnetbrightener/linq-to-sql-builder/releases/)


Inspiration
==========
I am a big fan of ORM, and I have been using Entity Framework since the first day I started my career as a .Net Developer back in 2009. 

Recently there is a project that I need to deal with 2 databases at the same time. For some reasons, I am not supposed to use Entity Framework for the second database which is dynamically configured in a tenant-based setting at runtime. So I have to choose either to come back to ADO.Net and making queries using string concatenation and SqlCommand, or I to come up with something that is friendly with Entity Framework usage, which is using Linq lambda expression to describe the query or command we want to process with the database.

Searching through the internet, I found a few repositories that seem to fit my needs, but I still reluctant because they all seem to miss something. For instance, the open-source library from [https://github.com/mladenb/sql-query-builder](https://github.com/mladenb/sql-query-builder) does most of the operations that we need for basic usages, but the queries and commands are built on top of strings.

Finally, I found the open-source repository at [https://github.com/DomanyDusan/lambda-sql-builder](https://github.com/DomanyDusan/lambda-sql-builder) and it's very close to what I am looking for. However, the author has not continued supporting the project and its last commit was 7 years ago by the time I started the project. So I decided to reference his code and make a modified version of what he has done, and adding support for INSERT, UPDATE, DELETE instead of only SELECT queries as in the original version.

This project is not meant to replace or to cover the entire SQL world, the purpose of this is to provide the most basic and commonly used operations like CRUD (Create / Read / Update / Delete) to the database from the application, which I believe it covers 70% the simple data access operations in most applications.

Continuing the spirit of original version, this version can be used to help you generate the query and parameters that you can use in ADO.Net with **SqlCommand** or you can use with **Dapper** to have a simple mapping back to your entities.

I would like to send my appreciation to the original author [DomanyDusan](https://github.com/DomanyDusan) and his tool. And I hope you guys, the developers, find my updated version helpful for your works/projects. All feedbacks and suggestions are welcome so that I can make this tool better and better.

.NET versions supported
===

At the moment the library supports .Net Core 2.1.

Installation
============

Install using Package Reference
---

1. Create a `nuget.config` in your project / solution folder with the following content:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <packageSources>        
        <add key="githubDotnetBrightener" value="https://nuget.pkg.github.com/dotnetbrightener/index.json" />
    </packageSources>
    <packageSourceCredentials>
        <githubDotnetBrightener>
            <add key="Username" value="[your_github_username]" />
            <add key="ClearTextPassword" value="[github_access_token]" />
        </githubDotnetBrightener>
    </packageSourceCredentials>
</configuration>
```

2. Replace `[your_github_username]` with your Github account, and `[github_access_token]` with your developer personal access token.

To generate your token if you do not have one, visit [Personal Access Tokens](https://github.com/settings/tokens), then click the [Generate new token] button. Make sure you select `read:packages` scope to be able to download packages from Github Packages. Once done, copy the generated token as it will no longer be shown to you once you leave this page.

3. Use the following command to install the package to your project
   
```
dotnet add [YOUR_PROJECT_NAME] package LinQToSqlBuilder
```

You can optionally specified version by using `--version [version]` parameter

Install manually
---

If you do not want to go through the Nuget configuration process, you can visit the [Releases](https://GitHub.com/dotnetbrightener/linq-to-sql-builder/releases) page and download the binary from there, then add reference directly to your project.

Usage
=====

## Simple Select

*Work In Progress*


## Select query with Join

*Work In Progress*

## Insert single record

*Work In Progress*

## Insert multiple records

*Work In Progress*

## Update a record

*Work In Progress*

## Delete a record / multiple records by condition

*Work In Progress*

Reference
=========

[https://github.com/DomanyDusan/lambda-sql-builder](https://github.com/DomanyDusan/lambda-sql-builder)

[https://github.com/mladenb/sql-query-builder](https://github.com/mladenb/sql-query-builder)