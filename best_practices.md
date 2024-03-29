# References
1. https://www.baeldung.com/maven-multi-module
2. https://www.smartics.eu/confluence/pages/viewpage.action?pageId=24511533
3. https://books.sonatype.com/mvnref-book/reference/pom-relationships-sect-pom-best-practice.html

# Best Practices
1. Grouping dependencies:
    1. use separate maven project with packaging type as “pom” to create logical group of related dependencies like hibernate, spring, mysql jdbc driver. These can be resued across different other modules. We can even manage multiple versions of these group dependencies project as me make changes in the dependencies like mysql to some another jdbc driver etc.
2. Mutti module project as aggregation
    1.  convenience to build all the sub modules from single place with single command (in right order) ------ top to down by specifying modules at top level. 
3. Multi module project as Inheritance
    1. avoid duplicacy/reuse shared configuration and dependencies across maven projects – bottom to up by specifying top level pom as parent in the sub modules. For example customer exposed webapp and internal admin web-app if using same tech stack like spring framework we can carve out shared stuff to parent and reuse accordingly
    2. Note: same multi module project can act as aggregated as well as inherited multimodule project
4. To customize the default behavior of Maven and supply some organization-specific information to configure deployment settings and build profiles, organizations define a top-level corporate POM that serves as the default parent when a project doesn’t have any good reason to depend on another
5. minimal duplication of configuration is a small price to pay for allowing projects like client-side and server-side to remain completely independent. 
