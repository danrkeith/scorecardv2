﻿# SCORECARD

## Video Demo

<URL>

## Running the Application

1. Navigate to the project directory.
2. Run the project locally.
	- For Windows:

			cd .\Publish
			start .\ScoreCardv2-win-x64

	- For MacOS:

			cd .\Publish
			chmod +x .\ScoreCardv2-osx-x64
			.\ScoreCardv2-osx-x64

	- For 64-Bit Linux (e.g. Ubuntu):

			cd .\Publish
			chmod +x .\ScoreCardv2-linux-x64
			.\ScoreCardv2-linux-x64

	- For 32-Bit ARM Linux (e.g. Raspbian)

			cd .\Publish
			chmod +x .\ScoreCardv2-linux-arm
			.\ScoreCardv2-linux-arm

3. Navigate to the URL specified in the console window.

## Description

### Summary

This website acts as a platform to keep score of card games. It is written to support the game '500', and also allows the user to simply add scores independant of any automated
scoring in the form of a 'Blank Game'. If a user is logged in, they are also able to resume their last 500 game or blank game.

The file structure is in the MVC (Model, View, Controller) format. The model files contain classes in which information is passed between the controller & view. The view files
contain the html files and layouts which are shown to the user and are generated client-side. The controller files run the server-side processing, such as data-accessing and
computations.

This website is written and built in C# in the DOTNET framework. Specifically, it uses the ASP.NET Core (MVC) framework that contains auto-generated files. All files that are not listed
below are those that are auto-generated by the framework.

### Base Directory

- ~\Encryption.cs - A file containing enxryption for passwords that are stored in the database. This file is not my own, and is credited in the references below.
- ~\SQLite.cs - Contains functions for commonly used SQLite operations.

### ~\wwwroot

- ~\wwwroot\app_data\Data.db - A SQLite database file that contains all user and game data.
- ~\wwwroot\css\site.css - The stylesheet applied to all html pages.
- ~\wwwroot\js\site.js - Contains a script to ensure that all necessary elements of a form are appropriately filled before allowing a user to continue.
- ~\wroot\lib - Contains files for the bootstrap and jquery libraries.

### ~\Controllers

- ~\Controllers\BlankGameController.cs - Manages all requests made associated with a blank game, including creating new rounds, showing rounds already played, and marking the game as 
completed. Is a child of the GameController class.
- ~\Controllers\FiveHundredController.cs - Manages all requests made associated with a 500 game, including creating new rounds, showing rounds already played, and checking for completion. Is a child of the GameController class.
- ~\Controllers\GameController.cs - Acts as a parent class for controllers for all games. Contains operations that are common between games, such as returning the view for the game, and creating new teams for the game. Does not contain unique functions that are game-specific, such as creating a new hand.
- ~\Controllers\HomeController.cs - Manages all requests that are made from the index of the website. Includes showing the home page.
- ~\Controllers\UserController.cs - Manages all requests that are associated with the user. Includes registering, logging in and out, & changing passwords

### ~\Models

- ~\Models\BlankGameViewModel.cs - Class for storing score inputs for Blank Games when adding new hands.
- ~\Models\FiveHundredViewModel.cs - Class for storing all required information when adding new hands in a game of 500.
- ~\Models\GameViewModel.cs - Class for carrying information from the controller to any game, containing all information that the user will see in the view.
- ~\Models\TeamsViewModel.cs - Class for storing the names of members of teams when creating a new game.
- ~\Models\UserViewModel.cs - Responsible for carrying information from the view to controller when performing any user-related function.

### ~\Views

- ~\Views\BlankGame\Game.cshtml - Contains the forn that allows hands to be added to BlankGames. Used in association with _GameLayout.
- ~\Views\FiveHundred\Game.cshtml - Contains the form that allows hands to be added to 500 games. Used in association with _GameLayout.
- ~\Views\Home\Index.cshtml - Acts as the home page for the website.
- ~\Views\Shared
	- ~\Views\Shared\\_GameLayout.cshtml - Displays the previously played hands for any game in a table. Acts as a layout which can be used to house a form for inserting new hands
	into a game.
	- ~\Views\Shared\\_Layout.cshtml - General-purpose layout applied to all webpages. Contains the heading navigation bar and the content that is always on screen.
	- ~\Views\Shared\GameIndex.cshtml - When creating any game, allows users to create teams of any size with any people in them.
- ~\Views\User
	- ~\Views\User\ChangePassword.cshtml - Page for changing passwords.
	- ~\Views\Login.cshtml - Page for loggin in.
	- ~\Vuews\Register.cshtml - Page for regestering a new user.

## Example Account Included

Username: `cs50`

Password: `harvard`

## References

- DOTNET (ASP.NET, SQLite.Net)
	- https://docs.microsoft.com/en-us/documentation/
- JQuery
	- https://www.w3schools.com/jquery/
- ~\Encryption.cs
	- https://www.c-sharpcorner.com/article/encryption-and-decryption-using-a-symmetric-key-in-c-sharp/
- Javascript Closures
	- https://stackoverflow.com/questions/21010963/how-to-get-outer-loop-index-inside-anonymous-function-call
- ASP.NET App settings
	- https://www.c-sharpcorner.com/article/reading-values-from-appsettings-json-in-asp-net-core/
	- ~\Controllers\UserController.cs Line 14-21
- SQLite iterative parameter insertion
	- https://stackoverflow.com/questions/2377506/pass-array-parameter-in-sqlcommand
	- ~\SQLite.cs Line 50-72
- Css Additions (~\wwwroot]\css\site.css)
	- https://codepen.io/jnbruno/pen/vNpPpW