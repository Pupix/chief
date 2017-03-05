# Chief
Keep in charge of your Polymer 2.0 application.

This is a set of behaviors to help keep a web components based application under control.
Instead of allowing any component to modify the application's data we use commands to do so.

**N.B. The application's elements must share a common prefix to interact with each other**
```html
<foo-element>
<foo-element2>
<bar-element>
<bar-element2>
```
Commands and state will not leak between the 4 elements, instead the elements will be treated as 2 different applications,
allowing for micro applications (widgets) creation within the same macro application without worrying about leakage.

There are 4 behaviors:
 - [Application](#application)
 - [Container](#container)
 - [Invoker](#invoker)
 - [Commander](#commander)
 
<a href="#application"></a>
### Application
The application entry point. It keeps track of the command registry and the application state.

You can register commands using `addCommand(name, handler)` or remove them using `removeCommand(name)`.

The invoked commands will receive the application's state as their first parameter followed by the `payload` received from an invoker.

<a href="#container"></a>
### Container
Containers provide the ability to read the application's state, receive updates about it and `invoke` commands.

<a href="#invoker"></a>
### Invoker
Invokers expose an `invoke(commandName, ...payload)` method that allows us to call defined application commands passing the payload as arguments to the commands.

<a href="#commander"></a>
### Commander
This provides a declarative way to bundle commands instead of programatically adding them.

--- 
##### References
- [Smart and dumb components](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0)
- [Redux](http://redux.js.org/docs/introduction/)
- [uniflow-polymer](https://github.com/google/uniflow-polymer)
- [app-behaviors](https://github.com/expandjs/app-behaviors)
