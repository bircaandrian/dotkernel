# Coding Guidelines

## Coding Standard
DotKernel 3 follows the rules described in `PHP-FIG` PSR-2 document.

### [PSR-2](../PSR/PSR-2.md)

## Entities and Collections

### Entity

The `entity` is the representation of an object.

##### Example:
* a `post`
* a `document`
* a `location`

#### Class Naming
Classes that represent entities are following the following structure:
 * Must start with the entity name
 * Must end with the word `Entity`
 * Must contain no other words unless they define a relation

##### Example:
 * `PostEntity` - represents a blog post
 * `DocumentEntity` - represents a document
 * `LocationEntity` - represents a location

> Note: our recommendation is to name the class attributes (object properties) the same as the column names in persistent storage (database)

### Colection

The `collection` is the representation of a list of objects.
Programatically speaking: a `collection` is an iterable set of `entities`. 


##### Example:
* a list of `posts`
* a list of `documents`
* a list of `locations`

#### Class Naming
Classes that represent entities are following the following structure:
 * Must start with the entity name,
 * Must end with the word `Collection`

##### Example:
 * `PostCollection` - represents a blog post list
 * `DocumentCollection` - represents a document list
 * `LocationCollection` - represents a location list
 


## Middleware just calls the code
Entities^TNE^ Classes^TNE^

The "Resources" or the "Middleware" should contain only base operation.
For instance, queries like `SELECT * FROM (...)` won't be written directly in the middleware
Code like `$db->select()->from()` will also be avoided when writing the middleware.


In PSR-7 applications `Interfaces` will be highly used. These interfaces only contain the `basic` / `common` behaviour.


POST
GET
PUT
PATCH
DELETE

Your `services`/`modules`^TNE^ will have interfaces for
If using `EMS` 

^TNE^ - term needs explanation