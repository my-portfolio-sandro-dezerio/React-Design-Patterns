# Hooks Pattern

Hooks API Provides super powers like state, context, refs and lifecycle to simple React Functional Components and make them special.

Any pattern like the container and presentational component allow us to separate concerns, containers frequently result in "huge components": components with a huge logic split across several lifecycle methods. And big components can be hard to read and mantain.

Since containers are written as class components, whey are not easily controlled. And when working with containers, we are also faced with other class-related problems such as autobinding and working the **this** keyword.

Now with the functional components we can access all the class related features, the Hooks aptterns solve the class-related problems mentioned above.

As pure JavaScript functions, functional components are controllable and eliminate the nuisance of working with **this** keyword.