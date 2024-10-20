# **Grant Sorenson's ePortfolio**
  I am Grant Sorenson and this portfolio represents my skills with examples in computer science. The first project represents teh culmination of knowledge while attending SNHU. 
# Project 1: SNHUBank ATM
## *Self-Assessment*

## *Initial Code Review*
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
This Artifact is called the SNHUBankATM and it is a .Net Maui application that acts as a BankATM for pre-generated data. I thought of this application in a systems design course at SNHU and ended up creating some system design documents about it. I thought it would be cool to create an entirely new project to show my skills, and decided a .Net Maui application would be the perfect framework for it. Originally, I was only going to use it for two categories, but as I created it I realized I would be able to create elements that fit perfectly into each one. A few skills I demonstrated that show my knowledge of software design and engineering include creating the entire app hierarchy and classes on paper and updating them as code is created. I understand how to design systems and how to use technologies to my advantage when designing those systems. For example, while creating this app I took advantage of the data generation tool mockaroo(Mockaroo - Random Data Generator and API Mocking Tool | JSON / CSV / SQL / Excel). With this tool I was able to generate all the data I would need to produce results easily with this application. Additionally, one of the reasons I chose mockaroo was because of its built in API that can be used with .Net maui. There could be functionality included for an administrator account that could create and add new accounts, and the information for those accounts could be generated without having to do anything else. Another technology I utilized was the community toolkit package for .Net Maui. With this package I was able to better implement the MVVM architecture by utilizing Object Collections. Another area it helped with was creating object accessors that allowed me to retrieve and set values while also providing a notify for when a property was changed. I decided to utilize .Net Maui because it was something I had little experience with, but I know how to code in c++ and have always wanted to learn c#. The MVVM architecture has three main components: The model, the view, and the view model. These components each serve a distinct purpose and operate via communication within the model. The view can be thought of as the front end of the application, wheile the model can be thought of as the data classes, and the viewmodel connects the two. For example, in this project we have a ViewModel AccountViewModel. This class is parented from a BaseViewModel in which we derive a few basic variables,
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

