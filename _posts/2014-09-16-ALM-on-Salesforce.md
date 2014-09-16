## [From Sandbox to Production: Demystifying Force.com Release Management Part 1 Webinar](http://www.youtube.com/watch?v=_5TY8lrOoQM)

* A Story about Customization and Deployment
  * CRM Enterprise Edition, no add on products.
  * Requirement to create custom order forms to track orders, update accounts, and contacts
  * Small IT department, 2 developers, admins wear many hats
  * Typical use case, need to track contracts, accounts, orders
  * Best practices:
    * if possible stay in the browser
    * using Apex or VisualForce?, use the developer console (getting the most attention)
    * do as much as you can with point and click
    * do as much as you can in the Sandbox first
      * isolate consultants from real data
  * ideally have one sandbox per developer
  * different types of sandbox
    * developer (just metadata, no object data)
    * configuration same as dev but larger storage (QA, training)
    * full, replica including all data (perf, scale, staging)
