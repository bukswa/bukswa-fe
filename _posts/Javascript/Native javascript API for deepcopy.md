# Deepcopy using Native Javascript API

###  structuredClone

The global structuredClone() method creates a deep clone of a given value using the structured clone algorithm.

The method also allows transferable objects in the original value to be transferred rather than cloned to the new object. 
Transferred objects are detached from the original object and attached to the new object; they are no longer accessible in the original object.

Syntax
```
structuredClone(value)
structuredClone(value, options)
```