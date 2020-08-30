# Functionalities of Paging library

- Keeps track of the keys to be used for retrieving the next and previous page.
- Automatically requests the correct page when the user has scrolled to the end of the list.
- Ensures that multiple requests aren't triggered at the same time.
- Allows you to cache data: if you're using Kotlin, this is done in a CoroutineScope; if you're using Java, this can be done with LiveData.
- Tracks loading state and allows you to display it in a RecyclerView list item or elsewhere in your UI, and easily retry failed loads.
- Allows you to execute common operations like map or filter on the list that will be displayed, independently of whether you're using Flow, LiveData, or RxJava Flowable or Observable.
- Provides an easy way of implementing list separators.

# Components of Paging library

- `PagingData` - a container for paginated data. Each refresh of data will have a separate corresponding PagingData.
- `PagingSource` - a PagingSource is the base class for loading snapshots of data into a stream of PagingData.
- `Pager.flow` - builds a Flow<PagingData>, based on a PagingConfig and a function that defines how to construct the implemented PagingSource.
- `PagingDataAdapter` - a RecyclerView.Adapter that presents PagingData in a RecyclerView. The PagingDataAdapter can be connected to a Kotlin Flow, a LiveData, an RxJava Flowable, or an RxJava Observable. The PagingDataAdapter listens to internal PagingData loading events as pages are loaded and uses DiffUtil on a background thread to compute fine-grained updates as updated content is received in the form of new PagingData objects.
- `RemoteMediator` - helps implement pagination from network and database.