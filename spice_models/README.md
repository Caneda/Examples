Spice Models
============

The examples in this folder show how to modify a component's model or use an external spice model. For every component there are basically three methods to modify a component's model:

  * Modify the basic parameters of the model.
  * Use a _model component_ and modify the needed parameters.
  * Include an external library file and use a model from the library.

## Modify the basic parameters of the model
The easier way to modify a component's behaviour is to modify the basic parameters of the model. In order to do so, include a component and edit its parameters with the required values.

## Use a model component
If you need to modify more parameters than those available in the basic parameters, you can include a _model component_. There are several _model components_ for different kind of devices including (but not limited to) transistors, diodes, transmission lines, switches, capacitors and inductors. You can also use this method if you have several components of the same type and you don't want to type the same parameter's values for each component. After you include the _model component_, edit its parameters and use its `name` as the `model` field (parameter) in every instance of the component.

## Include an external library file
A similar alternative to using a _model component_ is to include an external library file (a text file containing the model name and all the parameters' values) and use the model's `name` as the `model` field (parameter) in all the components needed. To include the external library file you can use the _library_ or the _include_ component. The main difference between an _include_ and a _library_ is that while in an _include_ you can have only one reference for each model (defining its parameters), in a _library_ you can have multiple references for each model (one in each library of the library file). In this way, for example, you could have a library with the typical, a library with the maximum and a library with the minimum parameters of a component (all in one file) and include the library you need in the simulation you are performing.

The advantage of using an external library file over the previous methods is that you can download the needed model or library from the web and use it directly in your design without needing to manually copy every parameter to a _model component_. This method is similar to that found in commercial simulation programs.

When using library files it is important to note that when using complex components described by spice subcircuits both the number of ports and the number of parameters must be equal between the symbol used and the model included in the library file. If using for example an opamp, and the number of pins between the spice library file and the symbol is not the same, a new opamp symbol must be created with the same number of pins as the component in the spice library file. This also holds true for the number of parameters (usually zero for a downloaded commercial model).

In this repository folder you will find some basic examples using the previously described methods. The included models in the provided examples are not based on real data, but rather manually modified for educational purposes only.