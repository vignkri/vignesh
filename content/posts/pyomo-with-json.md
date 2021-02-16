---
author: "Vignesh Krish"
date: 2021-02-16
linktitle: Using pyomo with JSON
title: Notes from using JSON with Pyomo
---

Using JSON with Pyomo is a pain due to couple of reasons. With simple models, the translation layer provided by Pyomo called `DataPortal` (2) works fine. However, with more complex interactions, the system probably will not allow flexibility. Here are a few notes to remember when using JSON with Pyomo:

- Remember to stick to standard JSON schema. This will allow you to parse values conveniently.
- If your model is simple and is not too nested, you can easily pass a standard JSON object to `DataPortal().load(filename=<name_of_file>)` to create your input data for the model.
- Pyomo does not support `numpy.float64` types. All types need to be standard Python types so remember to cast them to `float`. This can be checked using functions from numpy.
- For `AbstractModel` with `IndexedParam` in nested `Blocks`, it will be easier to write convenience functions to (a) parse the values correctly and (b) convert the indexed param to the correct dictionary format for Pyomo
- Use `to_json()` wherever possible to convert Pyomo objects to serializable and readable format

### References

1. [Dictionaries with Pyomo](https://pyomo.readthedocs.io/en/stable/working_abstractmodels/data/raw_dicts.html)
2. [DataPortals at Pyomo Documentation](https://pyomo.readthedocs.io/en/stable/working_abstractmodels/data/dataportals.html)