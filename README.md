# BareBonesRecyclerView
Simple implementation of a recycler view to expose all the components necessary in a straight forward manner and facilitate learning/recall. 

#Step 1: Gradle dependency
* add to Gradle app file: `compile 'com.android.support:recyclerview-v7:25.0.1`
* replace the version with something that fits your app

#Step 2: Create MainActiviy.java 
* add global references
  * RecyclerView (import it)
  * RecyclerAdapter (you'll write this class later)
  * LinearLayoutManger (import it)
  * Data (list of whatever you're trying to display, this project uses a simple array)
* in `MainActiviy.onCreate()`
  * set recyclerView reference to an id (you'll add this recycler view to xml later)
  * set RecyclerAdapter reference to a new RecyclerAdapter whose constructor takes in the data array
  * set linearLayoutManger to new LinearLayoutManager
  * set recyclerView adapter
  * set recyclerView layout manager
  
#Step 3: Add missing parts
* write recycler adapter class in new file (that `extends RecyclerView.Adapter<CustomHolder>`)
  (you'll write CustomHolder later)
  * implement methods
  * write constructor and set data to the constructor's input
  * add reference to data array
  * update `getItemCount()` to return size of data array
  * in `onCreateViewHolder()` inflate the item layout with an xml id that will be defined later and pass to CustomHolder's constructor to return it
  * in `onBindViewHolder()` set the fields of the holder based on the data and the position
  * write `CustomHolder` class inside the adapter class (extends RecyclerView.ViewHolder implements OnClickListener)
    * implement methods
    * write refs to what you want to display in each row of recycler view (defined in the xml file for the layout of each row, which we'll write later)
    * in constructor, set refs to fields in the xml we'll write later, findById() with future ids, and set the view's click listener to this
* write missing xml
  * add a RecyclerView widget to the xml of the main activity with the right id used in MainActivity
  * add a item xml layout file for the item to be displayed in each row of the recycler view, this will contain all the views that the `CustomHolder` requires
  
