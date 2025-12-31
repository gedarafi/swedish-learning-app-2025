
FUNC-REQ-LM-1: Learning Mode

ID and Name
FUNC-REQ-LM-1: Access Learning Mode
Date Created
9/25
Primary Actor
User
Secondary Actor
The system
Description
As a user,
I want to access a “Learning Mode” from the main menu,
so that I can learn the vocabulary involved in the next games.
Trigger
The user clicks on the button “Learning Mode”
Preconditions
The user sees the main menu of group 10 "Eat and Learn"
Postconditions
The N words played in the game are being marked as learned.


Normal flow
The user clicks on the button ‘’Learning Mode’’
The system displays one word randomly picked from a bag of words.
The user sees the image of the word, and clicks on the image. 
The system displays the spelling of the word in Swedish.
The user can and choose between ‘’got it’’ or ‘’repeat’’
If the user clicks on “got it”, the image won’t appear anymore.
If the user clicks on ‘’repeat’’ the world will appear once the user has checked all the 10 words.
The  system will present a new image and come back to step 3.
The user has completed all the 10 words.
The system redirects the user to level 1.
Alternative flows
The user clicks on the button ‘’Learning Mode’’
The system displays one word randomly picked from a bag of words.
The user sees the image of the word, and clicks on the image. 
The system displays the spelling of the word in Swedish.
The user clicks on the “Exit” button.
The system redirects the user to level 1.
Exceptions
If the system cannot load the audio and image resource due to a connectivity issue, it will display the error message: "Connectivity issue. Please reload the webpage.
Diagrams

User Requirement
REQ-LM-1: Access Learning Mode






ID and Name
FUNC-REQ-LM-2 Random Word Selection
Date Created
9/25
Primary Actor
User
Secondary Actor
The system
Description
The system shall present the user with 10 words randomly selected from a bag of words.
Trigger
The user has started the learning mode, and the system needs to display the first word.
Preconditions
The vocabulary database has been loaded
Postconditions
The front end it's able to render the image and presents it to the user in a friendly way according to the game design.
Normal flow
The user clicks on the button ‘’Learning Mode’’
The system will choose a random word for the bag of words using the random function from the Javascript’s math library.
A json file with all the information of the word is presented to the front end.
Id
Word in swedish
Image path
Sound path
Learned
Alternative flows
The user clicks on the button ‘’Learning Mode’’
If the system cannot select 10 words (e.g., fewer than 10 words available in the database)
	a. The system displays all available words instead.
	b. The user is notified: "Only x words available for learning"
The learning session proceeds with the available words.


Exceptions
The system doesn’t have a vocabulary loaded. The system displays the exception message “Error: No words loaded”
Diagrams

User Requirement
REQ-LM-2: Random Word Selection


ID and Name
FUNC-REQ-LM-1.3: Flashcard Functionality
Date Created
9/25
Primary Actor
User
Secondary Actor
System
Description
The system shall display a picture of a food item, and the user must be able to interact with it to see the Swedish word on the “back” of the flashcard
Trigger
The user clicks the flashcard
Preconditions
PRE-LM-1.3-1: The user has entered learning mode
PRE-LM-1.3-2: The user sees an image of the item they’re supposed to learn
Postconditions
POST-LM-1.3-1: The user can see and learn the swedish word of the object they have seen a picture of beforehand
Normal flow
The system turns the card, not showing the image anymore
The system shows the word that corresponds to the image on the page
Alternative flows
If the user does not click the flashcard within a certain time:

1. The system shall display a hint or prompt encouraging the user to interact with the flashcard.
Exceptions
FUNC-REQ-LM-1.3/EXCEPTION 1: The image cannot be displayed
The system displays the word of the object instead of the image
Diagrams

User Requirement
REQ-LM-3: Flashcard Functionality


ID and Name
FUNC-REQ-LM-1.4: User Feedback Mechanism
Date Created
9/25
Primary Actor
User
Secondary Actor
System
Description
The system shall display two buttons where one says “Got it” and other says “Repeat”, and the user must be able to interact with it and press either one.
Trigger
The user is in learning mode, and has been displayed a flashcard.
Preconditions
FUNC-REQ-LM-1.1, FUNC-REQ-LM-1.2, FUNC-REQ-LM-1.3
Postconditions
The user will be provided with the next flashcard
Normal flow
The user clicks on the button “Learning Mode”
The system shows two buttons.
The user clicks on either one of the buttons
The system shows a new flashcard but buttons stay the same.
Alternative flows
The system shows the two buttons from pressing either one of them
Exceptions
The system doesn’t have a vocabulary loaded. The system displays the exception message “Error: No words loaded” and no buttons are shown.
Diagrams

User Requirement
REQ-LM-4: User Feedback




ID and Name
FUNC-REQ-LM-1.5: Word progression logic
Date Created
9/25
Primary Actor
User
Secondary Actor
System
Description
The system shall if the user selects “Got it”, provide a new word, and the user will continue through the 10 words. If the user selects “Repeat”, the current word shall appear later in the session.
Trigger
The user clicks either the “Got it” or “Repeat” button
Preconditions
PRE-LM-1.6-1 The user has started the game
PRE-LM-1.6-2 The user is in learning mode
PRE-LM-1.6-3 The system have loaded the words and pictures from the “database”
Postconditions
POST-LM-1.6-1 A new flashcard shall be displayed
Normal flow
REQ-LM-1.5a 
System recognizes “Got it” button was clicked
The system removes the word from the pool of words in the session.
Alternative flows
REQ-LM-1.5b
System recognizes “Repeat” button was clicked
The system returns the current word back to the pool to be shown again later.
Exceptions
REQ-LM-1.6/EXCEPTION 1
The system doesn’t have a vocabulary loaded. 
The system displays the exception message “Error: No words loaded”.
Diagrams

User Requirement
REQ-LM-2: Random Word Selection


ID and Name
FUNC-REQ-LM-1.6: Exit Learning Mode
Date Created
9/25
Primary Actor
User
Secondary Actor
System
Description
The user shall be able to exit the learning mode at any point by pressing an "Exit" button or when it correctly “Got it” the 10 words.
Trigger
The user clicks either the “Exit” button or marks 10 words as “Got it”
Preconditions
PRE-LM-1.6-1 The user has started the game
PRE-LM-1.6-2 The user is in learning mode
PRE-LM-1.6-3 The system have loaded the words and pictures from the “database”
Postconditions
POST-LM-1.6-1 The user shall be in the menu of the game.
Normal flow
REQ-LM-1.6a 
The system recognizes that all 10 words of the session have been learned.
The system redirects the user to the menu.
Alternative flows
REQ-LM-1.6b
The system recognizes that the user has pressed the “Exit” button.
The system terminates the learning mode session and redirects the user to the main menu.
Exceptions
REQ-LM-1.6/EXCEPTION 1

The system doesn’t have a vocabulary loaded. 
The system displays the exception message “Error: No words loaded”
No buttons are shown.
Diagrams
 
User Requirement
REQ-LM-5: Exit Learning mode

---
@startuml Learning Mode Process Flow
!theme plain
skinparam backgroundColor white
skinparam activity {
    BackgroundColor lightblue
    BorderColor black
    FontSize 11
}
skinparam decision {
    BackgroundColor lightyellow
    BorderColor black
}

title Learning Mode - Complete Process Flow

start

:User clicks "Learning Mode" button;

:System attempts to load vocabulary database;

if (Vocabulary loaded successfully?) then (yes)
    
    :System selects 10 random words from database;
    
    if (Less than 10 words available?) then (yes)
        :Display notification "Only x words available for learning";
        :Use all available words;
    else (no)
        :Proceed with 10 selected words;
    endif
    
    :Initialize session:
    - Word counter = 0
    - Create repeat queue
    - Mark all words as "not learned";
    
    repeat
        :Display flashcard with food image;
        
        :Wait for user interaction;
        
        if (User action?) then (Clicks flashcard image)
            :Flip card - show Swedish word;
            :Display "Got it", "Repeat", and "Exit" buttons;
            
            if (User clicks which button?) then (Got it)
                :Remove word from current session;
                :Mark word as learned;
                :Increment learned counter;
                
            elseif (Repeat)
                :Add word to repeat queue for later;
                
            elseif (Exit)
                :Terminate learning session;
                :Redirect to main menu;
                stop
            endif
            
        elseif (Clicks Exit button)
            :Terminate learning session;
            :Redirect to main menu;
            stop
        endif
        
        if (All 10 words learned?) then (yes)
            :Session complete;
            :Redirect to Level 1;
            stop
            
        elseif (Current word pool empty AND repeat queue has words?)
            :Load next word from repeat queue;
            
        else (no)
            :Load next random word from session;
        endif
        
    repeat while (Session active?)
    
else (no)
    :Display error message: "Error: No words loaded";
    :No buttons shown;
    stop
endif

@enduml