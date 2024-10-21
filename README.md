# **Grant Sorenson's ePortfolio**
  I am Grant Sorenson and this portfolio represents my skills with examples in computer science. The first project represents teh culmination of knowledge while attending SNHU. 
# Project 1: FullStack Application SNHUBank ATM
## *Self-Assessment*

## *Informal Code Review*
### Artifact Background
  Initially for this project I was going to create separate artifacts that included the required functionality and displayed my skills effectively. However, as I continued work on the first artifact, I realized that I could implement every other category into it, so i did, and called it the SNHUBankATM. This Project started in a course called CS-255 Systems Design, and was only a small system on paper when the course was completed. It represented a banking ATM system in which a user could make actions like depositing and withdrawing money. It was a simple concept and I liked it because it would allow me to create something from scratch and show off as many skills as I could think of. A few of the technologies I decided to use were .Net Maui, MongoDB, Mockaroo, and a few other supplementary tools. It was difficult to decide what framework to use, but after some cursory research I decided to go with .Net with most of the code being written in c#.
### Code Assessment
  This project only existed on paper up until a few months ago, so the code review for this project is centered around some cursory pseudo-code and a few charts displaying action events and variables. Because of this, I had to start creating documentation for this system so I could build a solid foundation for the rest of the project. I knew .Net Maui framework used a Model View View-Model style architecture, so I created class outlines and charts based on this idea. The original content I had was undocumented and poorly outlined, so I had to create the classes and logic on paper. While it was difficult to create all of this, I felt it may have been slightly easier than starting with a codebase and content that had already been slightly written up. This allowed me to create freely and avoid problems that involved rewriting entire systems. 
  I do think the content that was initially created could have been better documented and had more examples of functionality. It should have had at least some additional proof of concept for some technologies that could be used to create such a system. Overall I thought going back and looking at what I had thought of was fun, and bringing it to fruition is a cool experience as the creator of this project. The video for the code assessment can be found [here](https://drive.google.com/file/d/1_1DMKCExLFkx1T6M0yr3TLTZCDzWt89c/view?usp=sharing), however within the video are projects that are no longer referenced by this assignment. 
### Planned Enhancements
1. **Software Design and Engineering:**
This project has been created from only a few design documents that I have created in another course, so to show my skills in software design and engineering I will create improved documentation for a desktop application created with .Net Maui and then implement those designs and create the application. This application will have a few different capabilities and will contain data that has been created using data generation software. This application is supposed to represent an ATM and will allow the user to select a preloaded account, login, view their accounts, and make actions on accounts. The supplied documents will outline the classes required and system design for how the application behaves and data is accessed. Overall these enhancements will show how I design and evaluate computing solutions that solve a given problem, demonstrate an ability to use well founded and innovative techniques, and develop a security mindset that anticipates adversarial exploits in software architecture and designs.
2. **Algorithms and Data Structures:**
This project will use custom data structures to create objects whose data is supplied from a database. The main data structures will represent a single UserAccount and include information about the user, including a collection of accounts, which will also include data like the type of account and balance. Additionally, each account will have a collection of histories, in which there will be information like the action type(deposit, withdraw), date, and amount. This data will need to be formatted if it requires user access, like the changing of an account balance or other user information. Formatting can require logic chains to reach the desired result, I will add some of these into the project to demonstrate algorithmic thinking. These enhancements will allow me to design and develop professional quality written visual communications, Demonstrate an ability to use well founded innovative techniques and skills, as well as develop a security mindset that anticipates adversarial exploits in software architecture.
3. **Databases:**
Because this project needs data to be interesting to interact with, it will need a database to pull that data from. I plan to implement a MongoDB database into the application and use a custom service class to process all of the requests. I will process the requests at an abstracted level so there is no easy way to access it, and it cannot be manipulated. The database will be in JSON and includes double nested elements as well as image url links that are operational. This will demonstrate my ability to Employ strategies for building collaborative environments that enable diverse audiences to support organizational decision-making in the field of computer science, Design and evaluate computing solutions that solve a given problem using algorithmic principles and computer science practices and standards appropriate to its solution while managing the trade-offs involved in design choices, and Develop a security mindset that anticipates adversarial exploits in software architecture and designs to expose potential vulnerabilities, mitigate design flaws, and ensure privacy and enhanced security of data and resources.  

## *Artifact - SNHUBankATM*
**Software Design and Enineering** [I will only do A for this first category, as the artifact description is that same for all 3]

  A. This Artifact is called the SNHUBankATM and it is a .Net Maui application that acts as a BankATM for pre-generated data. I thought of this application in a systems design course at SNHU and ended up creating some system design documents about it. I thought it would be cool to create an entirely new project to show my skills, and decided a .Net Maui application would be the perfect framework for it. Originally, I was only going to use it for two categories, but as I created it I realized I would be able to create elements that fit perfectly into each one. A few skills I demonstrated that show my knowledge of software design and engineering include creating the entire app hierarchy and classes on paper(Images can be found in the Images folder in the repo) and updating them as code is created, both of which incorporated my ability to design and evaluate computing solutions as well as employ strategies for building collaborative environments that can support organizations decision making. This was an important step for me because it allowed me to organize myself in a way that would allow me enough time to finish the project. System design is important in CS because not only does it allow to create systems, but it also helps you understand systems that you may have to go in and fix.
     
  B. Creating this system allowed me to display my skills of documentation and system planning. I understand how to design systems and how to use technologies to my advantage when designing those systems. For example, while creating this app I took advantage of the data generation tool mockaroo(Mockaroo - Random Data Generator and API Mocking Tool | JSON / CSV / SQL / Excel). With this tool I was able to generate all the data I would need to produce results easily with this application. Additionally, one of the reasons I chose mockaroo was because of its built in API that can be used with .Net maui. There could be functionality included for an administrator account that could create and add new accounts, and the information for those accounts could be generated without having to do anything else. Another technology I utilized was the community toolkit package for .Net Maui. With this package I was able to better implement the MVVM architecture by utilizing Object Collections and observable properties. Another area it helped with was creating object accessors that allowed me to retrieve and set values while also providing a notify for when a property was changed. I decided to utilize .Net Maui because it was something I had little experience with, but I know how to code in c++ and have always wanted to learn c#. The MVVM architecture has three main components: The model, the view, and the view model. These components each serve a distinct purpose and operate via communication within the system. The view can be thought of as the front end of the application in charge of the GUI, while the model can be thought of as the data classes, and the viewmodel connects the two. For example, in this project we have a ViewModel called AccountViewModel. This class is parented from a BaseViewModel in which we derive a few basic variables,
```c#
    public partial class BaseViewModel : ObservableObject, INotifyPropertyChanged
    {
        public BaseViewModel() 
        { 

        }

        [ObservableProperty]
        [NotifyPropertyChangedFor(nameof(IsNotBusy))]
        bool isBusy;

        [ObservableProperty]
        string title;

        public bool IsNotBusy => !isBusy;

    }
```
IsBusy is an observable property, which means that whener it changes we will be notified and perform some functionality, like 
```xaml       
  <ActivityIndicator IsVisible="{Binding IsBusy}"
            IsRunning="{Binding IsBusy}"
            HorizontalOptions="FillAndExpand"
            VerticalOptions="CenterAndExpand"
            Grid.RowSpan="2"
            Grid.ColumnSpan="2"/>
```
This is telling the activity indicator be active whenever the IsBusy variable is true which allows us to pull our data while controlling the visuals on the screen. Our Model on the other hand consists of a data class that is used to fill an observable collection. The program receives the data in a JSON list from the MongoDB server and translates it into UserAccount objects. With these objects we can supply data to XML components and hook notifies into different properties and collections.
```c#
    public partial class UserAccount
    {
        [BsonId]
        public ObjectId id { get; set; }
        public string password { get; set; }
        public string first_name { get; set; }
        public string last_name { get; set; }
        public string gender { get; set; }
        public string image { get; set; }
        public string email { get; set; }
        public string address { get; set; }
        public string pin { get; set; }
        public ObservableCollection<Account> accounts { get; set; }

    }
    public partial class Account
    {
        public string account_name { get; set; }
        public string account_balance { get; set; }
        public string account_number { get; set; }
        public ObservableCollection<AccountHistory> account_history { get; set; }
    }
    public partial class AccountHistory
    {
        public string date { get; set; }
        public string type { get; set; }
        public string amount { get; set; }
    }
```
Finally, our view is populated with xml objects and connected to a C# code behind that links functionality between the model and view through the view model. Bindings to data can be made here, or they can be created in xml if they don’t have to necessarily be dynamic. Overall the enhancements for the software design and engineering  category provided the app with increased functionality and best practice standards. The code was designed and documented with the advice of documents in mind. Some of the skills I displayed included utilizing libraries and tools to make my workflow more efficient and streamlined, creating the foundation for a system and transposing it to an actual framework, providing effective documentation, using pseudocode to segment functionality and make design trades, solve logic problems and implement solutions, articulate my approaches to solving problems and always had using best practices in mind.

C. While creating and improving this artifact I learned a lot of making the blueprints for a design and building it from top to bottom. I had to learn a lot in preparation for this project, which included me spending time reading up on a lot of documentation before making my documentation. This cut into development time, but it was worth it because I thought the system was easier to get the hang of. A few challenges I faced included choosing which technologies to use and the best way to implement them. After selecting .Net Maui as the main framework, I was happy to chose other technologes related to it because they have been In development for a while and are in use worldwide by many top companies. I incorporated feedback by pressing on and continuing to make what I set out to. I ended up using one artifact for every category, which was a decision I made when I started to realize the scope this project could encompass. The artifact was created and improved massively culminating in a functional application based on the idea. The user can view and interact with any account that is stored in the system, and that data will be saved and synced across the database network. The course outcomes I met included employing strategies for building collaborative environments that enable diverse audiences to support organizational decision making in the field of computer science, Design, develop, and deliver professional-quality oral, written, and visual communications that are coherent, technically sound, and appropriately adapted to specific audiences and contexts, and Demonstrate an ability to use well-founded and innovative techniques, skills, and tools in computing practices for the purpose of implementing computer solutions that deliver value and accomplish industry-specific goals.

**Algorithms and Data Structures**

B. With regards to Algorithms and Data Structures, I wanted to use this project because I knew I would have to interact with data structures a lot and create new ones to be successful In this project. One of the first things I did was make the class for the UserAccount slowly built up the data I thought they would need. For example, I added the name and password, then went on to address and pin and gender and email and so forth. All these properties act nicely with MongoDB and the ID property has been included and give the attribute [Bson] so it can be serialized correctly. These data structures are bound through xml as objects called ObservableCollections. These objects can contain lists of other objects and they generate code that tracks their properties and hooks notifies. These were bound using the ```CommunityToolkit.Mvvm.ComponentModel```. This module generates code that handles some of our viewmodel variables, which is nice for when a property needs to be updated and that has t0 be handled in real time.
```xaml
            <CollectionView ItemsSource="{Binding SelectedAccount}"  
                        x:Name="ListCV" 
                        Grid.Row="1"
                        Grid.Column="0"
                        VerticalOptions="Start"
                        HorizontalOptions="Center"
                        MaximumWidthRequest="800">
```
For example, this collection view is bound to the attribute SelectedAccount ,which is an attribute we have placed on the view-model, the in-between for the model and view.
```c#
public partial class AccountViewModel : BaseViewModel, INotifyPropertyChanged
 {
     public AccountService accountService;

     public ObservableCollection<UserAccount> Accounts { get; } = new();
     public ObservableCollection<UserAccount> SelectedAccount { get; set; } = new();
```
This connects the data that is our currently selected account, and the data that is displayed in certain aspects of the GUI thought the collection view. As an example, the login page has a number of collection views controlling the list on the left hand side and the data display that appears on the right when the user chooses an account selection. These are just a couple of ways I have incorporated different data structures into this project. I’m also manipulating a lot of data structures to do different things in multiple languages. For example, one of the things I figured I would do to add complexity to the project is connect the account that is being changed to an Enum. Not only does this allow me to use matching and have an easier time sending data, it protects me against using other types of iterators that couldn’t do the same thing. Another component that displays my use of algorithms is the logic that requires me to change balance through casts and appends. This code for example includes a number of different string operations that area all dedicated to getting the integer value, performing an operation, and then turning it back into a string and formatting it.
```c#
            //Find our entry
            var entryToUpdate = await collection.Find(new BsonDocument { { "_id", new ObjectId(currentSelectedAccount.id.ToString()) } }).FirstOrDefaultAsync();
            //clean our text so we can perform numerical operations, then convert back to monetary string
            string cleanText = new string(entryToUpdate.accounts[accountInd].account_balance.Replace("$", "").Trim());
            cleanText = cleanText.Replace(",", "");
            decimal newBalance = decimal.Parse(cleanText);
            //some variables we will need
            string newBalanceString;
…
newBalance += amount;
                newBalanceString = string.Format(CultureInfo.CurrentCulture, "{0:C}", newBalance);
```
A lot of the logic displayed in this application had to do with string concatenations and decision trees, most of which were planned ahead of time. I wanted to make sure that no errors were present, and the system functioned exactly as it had been planned. Additionally, this can serve as a basis for expansions like adding in different modes for an administrator or technician. The design of this architecture was built with best practices in mind and was essential for laying the groundwork for the rest of the application. One of the things I wanted to do with the data structure was base it off of the observable type from the community toolkit to make some variables easy to access. There are a number of improvements that were mentioned in the analysis that had to do with this section. Overall this enhancements will allow me to design and develop professional quality written visual communications, Demonstrate an ability to use well founded innovative techniques and skills, as well as develop a security mindset that anticipates adversarial exploits in software architecture. The enhancements applied that utilized these skills improved the artifact by making it more efficient at getting observable properties and providing the foundation for our main data objects. I was able to improve the user experience by incorporating asynchronous operations and applying changes in property value to hooks that can update underlying data which is relayed to the view from the view model. Overall this was a fun part of the project to make and I used my best judgment to make sure everything worked.

C. Enhancing the artifact for this kind of setup was difficult at first because I had the daunting task of learning the best practice of building upon .Net Maui. After I was able to look at he documentation and decide for myself how difficult it was going to be, I found that I could make a few adjustments and have my code working perfectly. I further looked Into .Net Maui tools I could use and stumbled upon the communitytoolkit MVVM model, and used that as a guide for the hierarchy of my data objects. I faced a few challenges like how to make accessor for certain variables in the base view model. Initially I was parenting the class from INotifyPropertyChanged but I opted to go with auto generated code from the CommunityToolkit. The artifact was improved by being able to process data coming from a source into objects that were accessible and could be acted upon. These objects are private and secure, and I was careful to incorporate security so the application could not be taken advantage of. A few of the course outcomes that I met during this enhancement included Demonstrate an ability to use well-founded and innovative techniques, skills, and tools in computing practices for the purpose of implementing computer solutions that deliver value and accomplish industry-specific goals, Develop a security mindset that anticipates adversarial exploits in software architecture and designs to expose potential vulnerabilities, mitigate design flaws, and ensure privacy and enhanced security of data and resources so the user accounts would be kept secure and data leakage would be kept to a minimum, and Design, develop, and deliver professional-quality oral, written, and visual communications that are coherent, technically sound, and appropriately adapted to specific audiences and contexts based on my designed for the data structures and how they would factor into the system as a whole.

**Databases**

B. While thinking about the different features I wanted the applicated to have, I decided to include a database because I found out it was compatible with .Net Maui. The extent to which I was able to implement the database was simply capped by my ability to create a suitable UI for it. Due to this there were some elements I wanted to create that I didn’t get to, but the main functionality for the application was created and I was connected using a Mongo database. To connect to the MongoDB database we use a client secret password and the package MongoDriver that is provided from mongo and packaged with the application. When working with a database its important that commands are correct, otherwise bad things could happened and data can get corrupted or erased. A few specific components in which I showed my CS skills included the data base creation, the connection, and the CRUD operations created for this project.
```c#
            const string connectionUri = "mongodb+srv://gdigidy98:{dbPass}@cluster0.nkmw7.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0";
            var settings = MongoClientSettings.FromConnectionString(connectionUri);
            settings.ServerApi = new ServerApi(ServerApiVersion.V1);
            client = new MongoClient(connectionUri);
            collection = client.GetDatabase("ATM_UserAccountsDB").GetCollection<UserAccount>("ATM_UserAccounts");

            try { 
            
                var result = client.GetDatabase("admin").RunCommand<BsonDocument>(new BsonDocument("ping", 1));
                Console.WriteLine("Pinged your deployment. You successfully connected to MongoDB!");
            }
            catch (Exception ex)
            {
                Console.WriteLine("Failed to Pinged your deployment. You successfully connected to MongoDB!");
                Console.WriteLine(ex);
            }
```
This was the best practice for connecting to the database and maintaining the necessary variables to change entries and certain elements. I also included error handling in case the elements were not found or there was an issue with connection. This was in the form of a ping in which I demonstrated my ability to use class objects correctly and improve the overall design of a project with them. All of these actions are done by the account service, so there is a layer of abstraction between the viewmodel and the sensitive data functions. This level of abstraction is important because it helps protect the data and gives the program increased security. Creating the Create Read Update and Delete operations allowed me to interact with the database and pull and update information. One of the most notable areas in the application that you can see this kind of functionality is in the account screen where the user and deposit and withdraw money. Data binding was also used to connect t elements from the backend to the front end of the application. This is evident in most of the application like the account list selections and the user data displays.

C. While creating this artifact I learned a lot about working with databases from MongoDB in .Net maui and how they can do many operations in the favor of the developer. It was difficult to get started with the databases and I ran into some trouble getting the actual cluster and collection, but once I figured out how to connect to the database I was able to pull information and make actions upon the database that were saved and relayed whenever I got the account list again. I worked to incorporate feedback by providing details of how I was creating the system and what I wanted to do with it. I wanted to use databases but I decided to MongoDB after SQLite was too difficult to work with. The issue I had with SQLite was it does not work well with data entries that have nested arrays or maps. This prevented from using the software despite it being an option for database. Overall I worked hard on this portion of the assignment because it was important for me that the user was able to interact with the database and the application refreshed the data seamlessly. The course outcomes that I sought to achieve were Employ strategies for building collaborative environments that enable diverse audiences to support organizational decision making in the field of computer science by choosing the DB tech early and reading up on it, Develop a security mindset that anticipates adversarial exploits in software architecture and designs to expose potential vulnerabilities, mitigate design flaws, and ensure privacy and enhanced security of data and resources by choosing DB software that was hackproof and extremely secure, Demonstrate an ability to use well-founded and innovative techniques, skills, and tools in computing practices for the purpose of implementing computer solutions that deliver value and accomplish industry-specific goals by implementing the Database to industry standards and keeping important data hidden behind a layer of abstraction.
