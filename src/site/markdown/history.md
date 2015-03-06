###  Version History

* **1.0.0**: Initial Version
* **1.0.1**: Added constrained-property plugin
* **1.0.2**: Added partial clone method generation
* **1.0.3**: Improvements in partial clone
* **1.0.4**: Added fluent builder and immutable plugins
* **1.0.5**: Added chainable fluent builder support
* **1.1.0**: New: `-Ximmutable`, Copy constructor support, fluent-builder copy from instance support, general fixes. Removed option to generate fluent builders without chained builder support.
* **1.1.1**: New: Type-safe selector support for partial clone/copy logic.
* **1.1.2**: Big fixes in selector logic
* **1.1.3**: Minor bug fixes in fluent-builder
* **1.1.4**: Fixed an error in fluent-builder where an initialization method wasn't properly overridden in derived builder classes, leading to the wrong builder type being returned when using chained sub-builders.
* **1.1.5**: Fixed error in Release Build process
* **1.1.6**: Fixed bug in group-contract plugin: Property names customised via binding info were generated incorrectly in the interface definitions.
* **1.2.0**: Major changes to the logic of partial cloning. The partial clone `PropertyTree` pattern replaces the previous `PropertyPath`, which had pretty unclear semantics. The new `PropertyTree` builders now just create a property tree, and on invocation of the "clone()" or "copyOf()" methods or the copy constructor, it is decided by an additional parameter whether the property tree should be considered an exclusion or an inclusion pattern. Additionally, the group-interface plugin has been modified to create interfaces also for the fluent builders, if the fluent-builder plugin is activated.
* **1.2.3**: Added "Copyable" interface and "createCopy" method which does the same thing as the "clone()" method, but doesn't suffer from the defective-by-design java.lang.Cloneable contract. It is planned to als add a "copyFrom" method to copy the state of another object into an existing object.
* **1.3.1**: Made fluent-builder plugin work in an "episode" (modular generation and compilation) context by also integrating compiled classes on the XJC classpath in the search for base and property classes.
* **1.3.6**: Also made group-interface work in an "episode" context, and fixed bug where empty interfaces were created if no implementation class for them could be found in the current module.
* **1.4.0**: group-interface is using its own episode file to maintain relationships to definitions in upstream modules. Command-line options for a specific plugin must now be given immediately after the plugin activation option ("-X..."). This way, name conflicts between plugin options are avoided. Static source files are generated via the JCodeModel.addResourceFile API, so a bug where the source files ended up in the root of the project tree should be fixed now. group-interface and fluent-builder now are working together more reliably.
* **1.5.0**: Added new Plugin "-Xmeta" to generate an inner class containing static meta information about the properties of a class. Internally, a common base class for plugins was extracted to help in command-line parsing and command-line documentation.
* **1.5.1**: Major updates to documentation, improvements to `-Xmeta` to expose static information about XSD definitions of properties.
* **1.5.2**:
    * Now hosted on Central
    * More updates to documentation
    * Customization of names of many generated source elements
    * Improved handling of CloneNotSupportedException in clone, copy, and fluent-builder plugins
* **1.5.3**:
	* Added maven "site" hosted on github pages
	* Improvements to javadoc comment generation
	* Improvements to documentation
* **1.5.4**:
	* Updates to generated documentation
	* changed groupId to net.codesup.util
* **1.5.5**:
	* immutable plugin: Added command line option to specify access level of default constructor
* **1.5.6**:
	* Added instance "newCopyBuilder" method generation
* **1.5.7**:
	* Fixed bug where partial copying in a builder didn't work
* **1.5.8**:
	* Bugfix: When generating builder interface, not all superinterfaces were declared in the "extends" clause.
	* Added command-line option to configure whether methods that could cause type clashes should be ommitted.
	* Added command-line option to configure suffix for instance fields of a builder holding sub-builders
