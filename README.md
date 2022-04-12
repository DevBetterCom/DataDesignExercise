# Data Design Exercise

Designing a database schema using normalization techniques.

## Instructions

Using the non-normalized data in the **BlogPost** table below, create a database schema that will represent the same data in 3rd Normal Form. When you're done, make a pull request to the upstream repo ([this one](https://github.com/DevBetterCom/DataDesignExercise)) so we can discuss in the PR comments.

### Blog Posts

| Slug                          | Title                                | Body           | AuthorName    | AuthorEmail                 | AuthorBio      | Category1            | Category2       | Tags                            | Views |
|-------------------------------|--------------------------------------|----------------|---------------|-----------------------------|----------------|----------------------|-----------------|---------------------------------|-------|
| serilog-structured-logging    | Structured Logging with Serilog      | Long Text Here | Eric Fleming  | ericfleming@nimblepros.com  | Long Text Here | Software Development | Cloud Computing | logging,serilog,appinsights     | 123   |
| persisting-smart-enum         | Persisting a Smart Enum with EF Core | Long Text Here | Kyle McMaster | kylemcmaster@nimblepros.com | Long Text Here | Software Development | null            | smartenum,efcore                | 234   |
| localization-aspnet-core-apis | Localization in ASP.NET Core APIs    | Long Text Here | Steve Smith   | steve@nimblepros.com        | Long Text Here | Software Development | Web APIs        | localization,aspnetcore,web-api | 345   |

[Table Generated with TableGenerator.com](https://www.tablesgenerator.com/markdown_tables#)

Fork this repository and add your tables here:

### BlogPost
| BlogPostId | Slug                          | Title                                | Body           |
|------------|-------------------------------|--------------------------------------|----------------|
| 1          | serilog-structured-logging    | Structured Logging with Serilog      | Long Text Here |
| 2          | persisting-smart-enum         | Persisting a Smart Enum with EF Core | Long Text Here |
| 3          | localization-aspnet-core-apis | Localization in ASP.NET Core APIs    | Long Text Here |


### Author
| AuthorId | AuthorName    | AuthorEmail                 | AuthorBio      |
|----------|---------------|-----------------------------|----------------|
| 1        | Eric Fleming  | ericfleming@nimblepros.com  | Long Text Here |
| 2        | Kyle McMaster | kylemcmaster@nimblepros.com | Long Text Here |
| 3        | Steve Smith   | steve@nimblepros.com        | Long Text Here |


### BlogPostAuthor
| BlogPostId | AuthorId |
|------------|----------|
| 1          | 1        |
| 1          | 2        |
| 2          | 3        |
| 3          | 2        |


### Category
| CategoryId | Category             |
|------------|----------------------|
| 1          | Software Development |
| 2          | Cloud Computing      |
| 3          | Web APIs             |


### BlogPostCategory
| BlogPostId | CategoryId |
|------------|------------|
| 1          | 1          |
| 2          | 1          |
| 3          | 1          |
| 1          | 2          |
| 3          | 3          |



### Tag
| TagId | Tag          |
|-------|--------------|
| 1     | logging      |
| 2     | serilog      |
| 3     | appinsights  |
| 4     | efcore       |
| 5     | smartenum    |
| 6     | localization | 
| 7     | aspnetcore   |
| 8     | web-api      |

### BlogPostTag
| BlogPostId | TagId |
|------------|-------|
| 1          | 1     |
| 1          | 2     |
| 1          | 3     |
| 2          | 4     |
| 2          | 5     |
| 3          | 6     |
| 3          | 7     |
| 3          | 8     |


### BlogPostView
| BlogPostId | Date       | Views |
|------------|------------|-------|
| 1          | 10/04/2022 | 123   |
| 1          | 11/04/2022 | 234   |
| 2          | 11/04/2022 | 345   |
| 1          | 12/04/2022 | 100   |


### Comment
| CommentId | Title             | CommentatorName | Comment           | BlogPostId |
|-----------|-------------------|-----------------|-------------------|------------|
| 1         | This is the title | PG Tips         | This is a comment |  1         |
|           |                   |                 |                   |            |


(your tables go here - you can use TableGenerator to create them. Include the data from the sample above in your tables)

## Extra Credit

Once you've completed the initial exercise, modify your design to support these additional features:

1. Blog posts can have one or many authors.
2. Users would like to see a report showing views per blog post per day.
3. Blog posts can have Comments. Each Comment should include a Title, Commenter Name, and Body.
