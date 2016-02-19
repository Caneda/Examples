Custom Library
==============

This example shows how to create a custom library with user created components.

In Caneda, libraries are simply folders with schematics and symbols inside. For each component created, both a schematic describing the electric circuit and a symbol with the component representation must exist. The connection between the schematic and the symbol is performed by the use of ports in both files. Each port in the schematic will be connected with the corresponding port in the symbol, matching both ports by name. Parameters may be exposed in the symbol and each parameter will be matched to a parameter in the schematic. In this case, the parameter name only in the schematic must be enclosed by brackets {} indicating a spice parameter operation. Mathematical operations are supported, giving extra flexibility.

For example, if a custom resistor was to be created, the symbol would contain the drawing, two ports and a parameter named `{R_custom}`. On the other hand, the schematic would contain the same two ports and a resistor (describing the simple electric circuit of a resistor) with a value `R={R_custom}`. In the same way, the value could be `R={R_custom*2/2}` using mathematical operations together with the parameter.

Finally, to add the recently created library to Caneda, open the _Application Settings_ dialog and in the _Libraries_ section add the custom created library by selecting its folder. Any successive change in the library will be reflected upon the next program restart. 

In this repository folder, you will find a couple of components created to show the previously described procedure. The example components are ready to use, and if you download the whole folder you can include it in your project by adding the folder as a library to Caneda.
