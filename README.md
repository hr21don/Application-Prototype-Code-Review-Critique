## Review, Refactor and Redesign an Application Prototype

Your team is developing Tinee, a simple text-based Ticket System for in-house use by your organisation.Users can create tickets to log various issues (e.g., bugs to fix, or Todos), which they or others can updatewith further information as the issue is resolved. Tinee is intended to be a lightweight utility that can bequickly integrated into other development projects, e.g., by running it from shell scripts, embedding it intoother applications, and so forth.

Tinee uses a basic client-server architecture:
* The server records a database of tickets, identified by tags.
* A ticket is essentially a list of tines (a portmanteau of “ticket message line”).Each tine contains the username of its author, and a single line of text as the message body.
* A client connected to a server can, e.g., read the existing tines for a tag, and add new tines.

Your teammates have developed a server in Java and, notably, message classes for the client-servercommunication. They have specified the above concepts (“tag”, “tine”, etc.) in more detail in the associatedJavadoc; e.g., see the Javadoc for the sep.tinee.server and the sep.tinee.message packages and theirclasses.To test the base framework and the server, they also wrote a makeshift client in Java. This client supportssome basic functionality, but it is buggy, incomplete and lacking any real design. By this, we mean softwaredesign – application architecture, design patterns, code structure, and development processes – as opposedto “user interface design” (also important, but not the topic of this module).

![Client-Application-Specification](Donso.jpg) 

Your organisation has also identified these features/extensions as requirements:
* Undo of (appropriate) commands in drafting mode.
* Support for internationalisation (i18n); e.g., UI messages in alternative languages.

##Robustness 
The command line client must support all existing and future functionality with gracefulhandling of user input errors (e.g., mistyped commands or invalid arguments). The UI should report usageerrors and continue running as expected, i.e., without crashing the session.

