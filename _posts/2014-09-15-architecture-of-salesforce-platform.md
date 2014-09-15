## [Understanding Multitenancy and the Architecture of the Salesforce Platform] (https://www.youtube.com/watch?v=jeysYua6ENs&list=UUMSfoJzq24tEKNfdB4GaIqg)

Trusted, Scalable Multi-Tenant Infrastructure

Salesforce does all the infrastructure, application services, operations etc.

* Multi-Tenancy
  * One cloud with many customers
  * one data store per Point of Depolyment (Pod)
  * 10k+ Customers per Pod
  * 50+ Pods
  * Data attached to org-id
  * What's in a Pod?
    * Shared Database
    * Metadata Cache -> every screen built each time
    * Query Optimizer (multi tenant aware)
  * Only this version and the next version of Salesforce
  * Everyone gets bug fixes
  * 260k tests run automatically on new features
  * 3 major releases per year, bug fixes each week
  * Key Architectural Principles
    * Stateless
    * Database system of record
    * No DDL at Runtime
    * Every RDBMS feature and trick
    * Objects tables stores metadata about custom objects
    * Data stored in Oracle to describe objects, fields, etc
    * Addtional tables used to index field values depending on type
  * Application Framework features:
    * field history, no audit penalty on Salesforce
    * validation rules and simple formulas
      * deterministic rules are indexed
    * rollup summary fields done automatically behind the scenes
    * Bulk processing
      * triggers are fired on up to 200 rows at a time
      * data definition is optimized to avoid performance hits or concurrency limits
    * Recycle bin
      * records smartly undeleted
    * Multi-tenant search
  * Query Optimization
    * deep awareness of pivot table structure
    * no runaway queries allowed
    * deep integration with the sharing model
    * lots of pre-query stuff to optimize and create multi-tenant aware queries on top of Oracle
    * considers stats on filter (where clause) and user access (how many rows you can see)
  * Apex code is stored as metadata
    * run on Apex Runtime interpreter
    * can limit everything as a result
    * 
  * http://developer.force.com/architect
  * http://developer.force.com/security -> security scanner
