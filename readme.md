# Bridgeway.Developer.Test

**Getting Started**

Make sure you have version 2.2 or later of .NET Core installed: [LINK](https://dotnet.microsoft.com/download)

Clone this repository.

In the root, run `dotnet restore`.

If using Visual Studio Code, it will add the necessary files to debug.

To compile and run the app, run `dotnet build` in the app root and in the 'bin/Debug/netercoreapp*' folder run `dotnet Bridgeway.Developer.Test.dll`. 

---

**General Notes**

This is a simple console app. The necessary infrastructure has already been written to allow dependency injection and to make the app run non-stop until CONTROL and C is pressed to cancel it.

Take note of *Startup.cs*. New services can be added to the application here. This is where you will plug your work into the app.

---

**The Project**

When the app starts a service runs called *HourlyActionService*. In this service a timer will call an action once an hour. It is up to you if you want to use this service to help acheive the below.

We want to have the ability to add classes to this project that will be called and run on specified days, at specified hours. For instance, we might want something to happen on Sundays and Wednesdays at 1400. For the purposes of this test, we will call this a *ScheduledAction*.

Please write the code that will enable us to do this within this project without using any external libraries. It should follow the object oriented rule of being open for extention but closed to change. 

Once up and running we should be able to add or remove a *ScheduledAction* and specify the day and hour-of-day we want it to run. The actions to be performed at the specified hours are not currently known, and it's anticipated the need for different actions will grow over time.

An example *ScheduledAction* might involve sending emails or updating a database. 

**Important:** As such, it should be possible to inject dependencies into the class or code that carries out the scheduled action, without having to 'new up'.
