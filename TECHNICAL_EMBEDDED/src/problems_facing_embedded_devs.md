# problems_facing_embedded_devs

This are problems facing embedded devs. We hope to solve them some day.  
All of the Information was obtained from a few posts across reddit, internet for real humans. 
reference : [this_page](https://www.reddit.com/r/embedded/comments/hhn0gh/what_are_the_worst_things_about_working_in/) 

1. Poor Documentation. It is hard to document a big project.
2. It sucks to inherit legacy code.
3. It sucks to inherit poorly documented code. Especially code whose modules are interrupt-driven
4. It sucks to use old inconvenient tools that have been passed with time, tools that only get used because compatibility and legacy preferences by the development team.
5. Embedded Engineers don't appreciate writing web/mobile apps. Web/mobile app development is too much noise, we want to build bare minimum websites...or none at all. A CLI app is enough.
6. SSL sucks
7. Some Electrical Engineers write code to get things quickly done... Not clean maintainable code. They are okay with C ad C++ and the broken tooling. Quick fixes everywhere. "From a 10,000 foot view, it looks like the industry is locked into C and with that C causes a lot of problems. Worse yet the firmware engineers do not know what problems C causes, because they have little or no experience in code bases outside of embedded. This often leads to dirty code bases that are not organized well or tested well. Likewise, there are TONS of run time errors in every embedded project I've seen. On the systems C++ level, the goal is to turn run time errors into compile time errors to minimize that hassle. This seems like a foreign concept to many firmware engineers so they're stuck struggling on these kinds of problems."


8. Expensive proprietary tools that are half-assed, fremium-based, non_standard(unnecessarily unique), replicas and unmaintained. And they sometimes get abandoned by the makers.
9.  Poor tools."Every manfacturer makes their own re-skinned version of Eclipse" to upstream tools designed for big machine development not playing nice with anything embedded, buggy debug adapters, buggy drivers, etc.
10. Cross Building, cross development, debugging, testing and deploying sucks... it is just tool after tool, configuration after configuration. Every company has their way of doing it... that sucks.
11. Makefiles, bashscripts, python scripts are hard to manage. Why cant things be plug and play. New devs build scripts above scripts... scripts that they did not fully read(because they are too many and reference too many libraries/tools).
12. "I want to conveniently work remote... cry.. cry... ha ha"
13. "At my current job what I hate most is being managed by people from CS background that never did embedded in their life.
Having to convince my manager that you can't train an ML model in a Cortex M0 at 24MHz with 350 kb flash and was only one of the highlights. And I dont have a clue about ML."

1.  "Pay is often far worse than what a less skilled web dev will ever make.... I mean the shear complexity of custom embedded development vs centering a div...cmon guys" 
2.  Crappy tooling. More crappy tooling
3.  Crappy Tooling.
4.  "Not everyone gets to code, and maybe the coding part is relatively small compared to documenting and designing" - we became embedded engineers to code, this hurts.
5.  proprietary everything : Tools, ISAs, F* everything. It's normal to not give you documentation for a device unless your company has special business relationships with the vendor. Or not having documentation at all - why bother when there's a proprietary tool that generates the code for you?
6.   Embedded Devs are hard-headed, each of us has ideals and opinions, everyone expects the other to understand their development choices. Embedded developers are like developers squared,  If business managers decide to get rid of developers, high-level developers in turn think of getting rid of embedded developers...the hard-headed team members (they can't even work under scrum properly!)
7.   The absolute monumental struggles of the embedded world's debug, testing, and build systems. 
8.   BAD DOCS. And i don't necessarily mean information missing (although that also happens quite often) but rather every vendor having their own system of documentation, naming etc.