#### Introducing DDD
  * High Level View of DDD 1: Interaction With Domain Experts
    * cultivate your ability to communicate with business people
  * Focus on a SubDomain
    * divide and conquer, splitting the problem into subdomains
  * Implementing the SubDomain
    * seperation of concerns, focusing on the domain, not the infrastructure
  * Benefits of DDD
    * flexible
    * customer's vision/perspective
  * Drawbacks of DDD
    * time and effort
      * discuss & model the problem with domain experts
    * learning curve
    * ddd is to help with complex business requirements, not just technical complexity
  * Key Takeaways
    *  solving complex problems
    *  understand client needs
    *  efficient and effective path to solution
  * Resources
    * DDD, Applying DDD and Patterns, Implementing DDD 

#### DDD: Modeling Problems in Software
* Learning about our domain by talking with a domain expert
  * important to have a continuous conversation with the domain expert
  * work with client to discover sub-domains
* Breaking the domain into sub-domains
  * what's in and out?
* Focusing on One sub-domain with the domain expert
  * working out terminology (Clients vs patients(pets)), appointments, office visit or surgery, dependencies between them etc.
  * who is involved? 
  * Are these terms ok? Resources = Doctors etc
* First high-level model of the sub-domain
  * appointment management
  * some parts are going to be used elsewhere too, like patients
* Creating a Bounded Context
  * where is this model valid?
  * even same name concepts may not work in another context
  * Client is simple in Appointment scheduling but more complex in Billing
  * Keep them model strictly consistent within its bounded context
  * Explicitly define contexts, seperate views of the same model in each
    * at the extreme seperate teams, etc.
    * in reality do namespaces, folders, projects
  * Difference between sub-domain and bounded context
    * they look alike, sub-domain is business (problem), bounded context is software size
    * carpet to floor analogy, carpet shaped to fit the floor
    * in a fresh solution they tend to correlate closely
  * Understanding Context Maps
    * Which concepts refer to the same entity? eg. client
    * which are different things? -> appointment notification vs billing notification
    * what can each team change seperately?
    * common approach is to have a shared kernel as the agreed shared model
  * Clearly defined context boundaries are hard and a common stumbling block
  * Bounded context in our application
    * Cross cutting concerns? -> SharedKernel folder
  * The Ubiquitous language of a bounded context
    * team and business people need to speak the same language
    * remove the translation step requirement
    * explain back to the business person what you think they said
  * Working on a ubiquitous language with the domain expert
    * sit down and sort out confusing terms with the domain expert
    * client -> person who makes appointment, pays the bills, brings pets to clinic
    * Patients -> animal for whom medical records are kept
    * what's a surgery vs office visit etc.
  *  Glossary of terms from this module
    * problem domain -> specific problem the software you're working on is trying to solve
    * core domain -? something the customer must do well and cannot outsource
    * context mapping -> process of identifying bounded contexts and their relationships
    * shared kernel -> part of the model that is shared by two or more teams, who agree not to change it without collaboartion
    * ubiquitous language -> language using terms from the domain model that programmers and domain experts use to discuss the system
      * use throughout a bounded context 
