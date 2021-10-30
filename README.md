# assignment challenge 10
<h1> Team-Profile-Generator</h1>
<h1> Project Description</h1>
<p>  The Team Profile Generator is a command-line-input application run in Node that requests information<br/>
from the user about members of an engineering team and generates an HTML file displaying that information.<br/>
Before running the application the user must perform an npm install to install all required dependencies.<br/>
Upon launching the app, the user is asked to describe the first member of their team. The user enters the team member's name,<br/>
selects that member's role from a list (options include "Engineer," "Intern," and "Manager), enters the member's ID (any string),<br/>
enters the member's email address, and then must enter another piece of information that will differ depending on what role was selected.<br/>
If "Engineer" was selected, the app asks the user for the team member's GitHub username; if "Intern" was selected, the member's school is requested; <br/>
and if "Manager" was chosen, the user is prompted for the team member's phone number.<br/>
A screenshot showing an example user input is shown below:<br/>
  <img src="./assets/images/Screenshotappplication.png">
  
  
  
  When all information on the team member has been entered, the user is asked whether there are any more members they would like to add. If so, the user is asked the same questions about the new team member. If not, an HTML file is created with cards displaying the information on all the team members entered by the user in the "outputs" folder titled "team.html." <br/>A screenshot of an example team profile is shown below:
   <img src="./assets/images/Screenshotteam.png">
</p>
<h1>Techniques and Technologies Used</h1>
<p> This app was created using Object-Oriented Programming concepts, namely using classes and constructors to create "team member" objects based on information entered by the user. The app is run using Node.js, and uses the "Inquirer" and "FS" node modules. Files for different objects are also stored in separate .js files and passed among one another using module.exports and require.

This app uses concepts from Test-Driven Development. Jest is used to perform tests on all the class constructors to ensure that they behave as expected. The FS node module is used to generate an HTML file from strings written in JavaScript. Since the app will work no matter how many team members the user adds to the system, the HTML is built in a piecemeal fashion, starting with the head and part of the body. For each team member object created, a new column with a card inside containing the team member information is added. Then when the last member has been added, the last bit of the HTML is added to the file. One complication experienced during this process was that since the fs.appendFile method is asynchronous, the bottom part of the HTML could be added before the HTML containing information on the last team member had been added. In order to deal with this, the function that adds the team member information to the HTML was converted into a promise, and only once the promise was resolved would the bottom part of the HTML be added to the output file.     </p>
