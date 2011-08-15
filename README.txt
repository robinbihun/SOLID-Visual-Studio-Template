This is a simple Project Setup that is designed to enforce the SOLID principles.

Core:
	Depends On: Nothing
	Provides: Abstractions for your entire app, there should not be any references to anything "process wise"

DependancyResolution:
	Depends On: Core, DataAccess, BusinessLogic
	Provides: A proxy for your IoC container so that you can contain all your IoC specifics in one place.

DataAccess:
	Depends On: Core
	Provides: All implmentations for your data access.

BusinessLogic:
	Depends On: Core, (any 3rd party services)
	Provides: All implementations for any business logic, this layer can also depend on outside 3rd party services or processes.

{PUBLIC}:
	Should only Depend On: Core, DependancyResolution
	This is where all your public facing projects should reside here - WCF services, MVC apps, WebForms

UnitTests:
	Depends On: Core, DependancyResolution, DataAccess, BusinessLogic, and Any Public facing apps
	Provies: Unit tests for all your applications, if you wish to split this into multiple test projects for larger apps, feel free.