# Issues with current implementation

## From a usability perspective, we have the following issues:

- The user has no information on the list loading state: they see an empty screen when they search for a new repository or just an abrupt end of the list while more results for the same query are being loaded.
- The user can't retry a failed query.

## From an implementation perspective, we have the following issues:

- The list grows unbounded in memory, wasting memory as the user scrolls.
- We have to convert our results from Flow to LiveData to cache them, increasing the complexity of our code.
- If our app needed to show multiple lists, we'd see that there is a lot of boilerplate to write for each list.