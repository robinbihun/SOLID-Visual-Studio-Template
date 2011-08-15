This assembly is used primarily as a Proxy for your IoC container, this way you do not need to have references or calls to a specific IoC container sprinkled throughout your code.

Any refrences to Unity, Ninject, Castle Windsor, etc should be in this assembly and you should have a (proxy) class you call to access that particular container.
This way it is easy to change from one IoC container to another with minimal code changes.