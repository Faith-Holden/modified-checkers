# modified-checkers

My solution for Chapter  Exercise  of “Introduction to Programming Using Java”.
Implementation notes: This is an edited version of Checkers.java, a class provided
by the textbook's author. I added save and load functionality, including methods, variables,
and listeners.

NOTE: This is a javafx program. It requires the javafx library as a dependency.
(See bottom of this README for javafx instructions).

Problem Description:
The sample program Checkers.java from Subsection 7.5.3 lets two players play checkers.
It would be nice if, in the middle of a game, the state of the game could be saved to a file.
Later, the file could be read back into the file to restore the game and allow the players to
continue. Add the ability to save and load files to the checkers program. Design a simple
text-based format for the files.It’s a little tricky to completely restore the state of a game. The program has a
variable board of type CheckersData that stores the current contents of the board, and it
has a variable currentPlayer of type int that indicates whether Red or Black is currently
moving. This data must be stored in the file when a file is saved. When a file is read into the
program, you should read the data into two local variables newBoard of type CheckersData
and newCurrentPlayer of type int. Once you have successfully read all the data from
the file, you can use the following code to set up the program state correctly. This code
assumes that you have introduced two new variables saveButton and loadButton of type
Button to represent the “Save Game” and “Load Game” buttons:
board = newBoard; // Set up game with data read from file.
currentPlayer = newCurrentPlayer;
legalMoves = board.getLegalMoves(currentPlayer);
selectedRow = -1;
gameInProgress = true;
newGameButton.setDisable(true);
loadButton.setDisable(true);
saveButton.setDisable(false);
resignButton.setDisable(false);
if (currentPlayer == CheckersData.RED)
message.setText("Game loaded -- it’s RED’s move.");
else
message.setText("Game loaded -- it’s BLACK’s move.");
drawBoard();

Javafx setup instructions:
Download javafx from: https://gluonhq.com/products/javafx/ (I used javafx 12). Save it to a location of your choice.
Unpack the zip folder.
Open my project with your IDE of choice (I use intellij IDEA).
Add the javafx/lib folder as an external library for the project. For intellij, this means going to "project structure" -> "libraries" -> "add library" ->{javafx location}/lib
Add the following as a VM argument for the project: --module-path "{full path to your javafx/lib folder}" --add-modules javafx.controls,javafx.fxml,javafx.base,javafx.graphics,javafx.media,javafx.swing,javafx.web
Build and run the project as normal.
