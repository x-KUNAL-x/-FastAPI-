# -FastAPI-

Recap¶
In summary, you declare once the types of parameters, body, etc. as function parameters.

You do that with standard modern Python types.

You don't have to learn a new syntax, the methods or classes of a specific library, etc.

Just standard Python.

For example, for an int:


item_id: int
or for a more complex Item model:


item: Item
...and with that single declaration you get:

Editor support, including:
Completion.
Type checks.
Validation of data:
Automatic and clear errors when the data is invalid.
Validation even for deeply nested JSON objects.
Conversion of input data: coming from the network to Python data and types. Reading from:
JSON.
Path parameters.
Query parameters.
Cookies.
Headers.
Forms.
Files.
Conversion of output data: converting from Python data and types to network data (as JSON):
Convert Python types (str, int, float, bool, list, etc).
datetime objects.
UUID objects.
Database models.
...and many more.
Automatic interactive API documentation, including 2 alternative user interfaces:
Swagger UI.
ReDoc.
Coming back to the previous code example, FastAPI will:

Validate that there is an item_id in the path for GET and PUT requests.
Validate that the item_id is of type int for GET and PUT requests.
If it is not, the client will see a useful, clear error.
Check if there is an optional query parameter named q (as in http://127.0.0.1:8000/items/foo?q=somequery) for GET requests.
As the q parameter is declared with = None, it is optional.
Without the None it would be required (as is the body in the case with PUT).
For PUT requests to /items/{item_id}, read the body as JSON:
Check that it has a required attribute name that should be a str.
Check that it has a required attribute price that has to be a float.
Check that it has an optional attribute is_offer, that should be a bool, if present.
All this would also work for deeply nested JSON objects.
Convert from and to JSON automatically.
Document everything with OpenAPI, that can be used by:
Interactive documentation systems.
Automatic client code generation systems, for many languages.
Provide 2 interactive documentation web interfaces directly.
We just scratched the surface, but you already get the idea of how it all works.

Try changing the line with:


    return {"item_name": item.name, "item_id": item_id}
...from:


        ... "item_name": item.name ...
...to:


        ... "item_price": item.price ...
...and see how your editor will auto-complete the attributes and know their types:
