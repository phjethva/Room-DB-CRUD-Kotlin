# Room-DB-CRUD
It is an example for Android to store date in Room Database with basic CRUD operation.

# Example:
Here in this tutorial we try to do an example of To Do list. You can find the structure of Room Database in below table.

| Id (AI) | TaskName |  TaskDateTime  |
|:-:|:-:|:-:|
|    1    |  Task 1  | dd/MM/yyyy kk:mm:ss |
|    2    |  Task 2  | dd/MM/yyyy kk:mm:ss |
|    3    |  Task 3  | dd/MM/yyyy kk:mm:ss |
|    4    |  Task 4  | dd/MM/yyyy kk:mm:ss |
|    5    |  Task 5  | dd/MM/yyyy kk:mm:ss |

We will follow these below steps to understand CRUD operations of Room Database.

### Step 01:
- Base components for Room database in Android is:
  1) **Database:**
     - It contains the holder and serves as the main access point for the connection.
     - It is an abstract class extends with RoomDatabase and annoted with @Database.
  2) **Entity:**
     - It represent the table within the database.
  3) **DAO:**
     - It contains the method used for accessing the database.
  4) **Repository:**
     - It is used to managing multiple data sources.
  5) **ViewModel:**
     - It works as a communication between Repository and UI.
  6) **LiveData:**
     - It is a data holder class. It observes automatically when data has changed.
- We will manage three values in database:
  1) **Id (Auto Increment)**  : It is an unique id of Task created.
  2) **TaskName**             : It is a name of Task.
  3) **TaskDateTime**         : It is a date & time of Task created.

Now We will manage datbase query for different CRUD operation for this created table.

### Step 02 : CREATE
- Create new task.
- We will create a method named **"createTask()"**.
- method **"repositoryTask.createTask(model)(...)"** will insert entry in to created database.

### Step 03 : READ
- Read all task or task by ID.
- We will create three methods for different read related operation.
  1) **"getTotalTaskCount()"** : It will give count of total entries available in database.
  2) **"readAllTask()"**       : It will read all entries available by values in database.
  3) **"readTaskByID()"**      : It will read entry by given id if available in database.
- Here most important thing is you will get return data in **LiveData** class, so you need to formate it. For this you can use **Observer** class methods.
- Use below method for observing **LiveData**:
  1) This method will return multiple data:
  ```
  repositoryTask.readAllTask().observe(ActivityMain.this, new Observer<List<ModelTask>>() {
      @Override
      public void onChanged(List<ModelTask> models) {
      }
  });
  ```
  2) This method will return single object:
  ```
  repositoryTask.readTaskByID(...).observeForever(new Observer<ModelTask>() {
      @Override
      public void onChanged(ModelTask model) {
      }
  });
  ```
  
### Step 04 : UPDATE
- Update task.
- We will create a method named **"updateTask()"**.
- method **"repositoryTask.updateTask(model)"** will updte enter of given id by necessary values in to database.

### Step 05 : DELETE
- Delete task.
- We will create a method named **"deleteTask()"**.
- method **"repositoryTask.deleteTask(model)"** will delete entry of given id in to database.

Read more about Room database operations in Android here: [Room](https://developer.android.com/training/data-storage/room)

# Thanks for you Time & Consideration.
If you feel that this tutorial really helps you than give me a like by clicking above 🟊 STAR button.

You can buy me a coffee for my work by clicking this link: [Buy Me a Coffee on PayPal](https://www.paypal.me/phjethva)
