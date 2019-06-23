/*$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$
$  Alexander Au                 $
$  10/23/2017                   $
$  Test cases                   $
$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$*/

/**/

#include <iostream>
#include <windows.h>
#include <ctime>
#include <conio.h>
#include <stdlib.h>
#include <iomanip>
#include <string.h>
#include <math.h>

using namespace std;


int main()
{
	
	int win=0 , tablesize1, reset, tablesize2, card, compchoice, cardchoice, loss=0, playcard , playcard2,  compcard, compcard2, acechoice, secretcard; /*Declare several ints*/
	char quit='Y'; /*Declare a char for use in the while loop*/
	int playtotal=0, comptotal=0; /*Sets the player's card total and the computer's total to o*/
	string drawchoice; /*Sets a string for use later*/
	
	srand(time(NULL)); /*Sets a true randomiser for the rand function*/
	string stop; /*sets a string for later*/
	
	secretcard=rand() %7+3; /*Use to add a secret value to the computer's draw so they will almost never go over 21*/
	

	
	cout << "Welcome to the Stallion Casino!\n"; /*Output to the uer*/
	cout << "You'll be participating in an unvoluntary game of 21 today!\n"; /*Output to the user*/
	
	
		while ((quit!='N')  && (loss!=10)) /*While loop to keep the player in until they want to quit or loe 10 hands*/
		{
	
		cout << "Which ace value woud you like? [1(1)/2(11)]\n"; /*Asks for an ace value*/
		cin  >> acechoice; /*User input*/
		if (acechoice==1) /*Sees which ace value they want and sets all the cards to that value excluding the one they didn't want*/
		{
		playcard2=rand() %10+1; 
		playcard=rand() %10+1;
		compcard2=rand() %10+1;
		compcard=rand() %10+1;
		playtotal=playtotal+playcard+playcard2; /*Sets the player card total*/
		comptotal=comptotal+compcard+compcard2; /*Sets the computer's card total*/
		
		if (comptotal < 15) /*Adds a secret value since casino people are cheaters*/
		{
			comptotal=comptotal+secretcard;
			
			
		}
		}
		else if (cardchoice==2) /*Sees which ace value they want and sets all the cards to that value excluding the one they didn't want*/
		{
		playcard2=rand() %11+2;
		playcard=rand() %11+2;
		compcard2=rand() %11+2;
		compcard=rand() %11+2;
		playtotal=playtotal+playcard+playcard2; /*Sets the player card total*/
		comptotal=comptotal+compcard+compcard2; /*Sets the computer's card total*/
		
		if (comptotal <= 15) /*Adds a secret value since casino people are cheaters*/
		{
			comptotal=comptotal+secretcard;
			
			
		}
		}
		cout << "Your cards are: " <<playcard<< " and " <<playcard2 << "\n" ; /*Outputs the cards you have*/
		
		cout << "Which of your opponent's cards would you like to look at? [1/2]\n"; /*Asks the user which of the opponent's cards they wish to see*/
		cin  >> compchoice; /*Gets the user's choice*/
		
			
		if (compchoice==1) /*If the user decides to pick the first card*/
		{
			cout << "You decided to look at their first card, which is: " << compcard << "\n\n";
			
			
		}
		else if (compchoice==2) /*If the user decides to pick the first card*/
		{
			cout << "You decided to look at their second card, which is: " << compcard2 << "\n\n";
			
		}
			while (drawchoice!="No") /*While loop for when the wish to stop drawing cards*/		
			{
			std::cout << "Your card total is: " <<playtotal<< "\n"; 
			cout << "Would you like another card? [Yes/No]\n";
			cin >> drawchoice; /*Gets the user's choice*/
			
			playcard2=rand() %10+1; /*Rerandomizes the cards*/
			playcard=rand() %10+1;

			
			if (drawchoice=="Yes") /*If the user want to draw another card*/
			{
			cout << "You drew: " <<playcard << "\n"; /*Shows the user which card they drew*/
			playtotal=playtotal+playcard; /*Updates the playtotal*/
			
			}
			}
			
			if (drawchoice=="No") /*When they decide to stop drawing cards*/
			{
				
			if (playtotal >= 21) /*If you total is above 21*/
			{
				cout << "You lost, your total was: " << playtotal << " which is higher than 21.\n"; /*Displays yout total*/
					cout << "The dealer's total was: " << comptotal << ".\n"; /*Displays the comp's total*/
				loss=loss+1; /*Adds one to the loss counter*/
				cout << "Would you like to play again? [Y/N]\n"; /*Asks if they want to play again*/
				comptotal=0; /*Sets the comptotal back to 0 for the new round*/
				playtotal=0; /*Sets the playertotal back to 0 for the new round*/
				drawchoice.erase(1,8); /*Sets drawchoice back to nothing aka sends it to the 21 equivalent of the shadow realm*/
				cin >> quit; /*User input*/
				system ("CLS"); /*Clears the screen*/
				
			}
			
			
				else if  ((comptotal > 21) && (playtotal < 21)) /*If the comp's total is above 21 and yours in under 21*/
			{
				cout << "You won, your total was: " << playtotal << " which is lower.\n"; /*Displays yout total*/
				cout << "The dealer's total was: " << comptotal << " which is higher than your total but they're over 21.\n"; /*Displays the comp's total*/
				win=win+1; /*Adds one to the win counter*/
				cout << "Would you like to play again? [Y/N]\n"; /*Asks if they want to play again*/
				comptotal=0; /*Sets the comptotal back to 0 for the new round*/
				playtotal=0; /*Sets the playertotal back to 0 for the new round*/
				drawchoice.erase(1,8); /*Sets drawchoice back to nothing aka sends it to the 21 equivalent of the shadow realm*/
				cin >> quit; /*User input*/
				system ("CLS"); /*Clears the screen*/
			
			}
			
			else if ((playtotal < 21) && (comptotal < 21) && (comptotal < playtotal)) /*If both the comp and you are under 21 but you have the higher total*/
			{
				cout << "You won, your total was: " << playtotal << " which is higher than the opponent's and lower than 21.\n"; /*Displays yout total*/
				cout << "The dealer's total was: " << comptotal << " which is lower than your total.\n"; /*Displays the comp's total*/
				win=win+1; /*Adds one to the win counter*/
				cout << "Would you like to play again? [Y/N]\n"; /*Asks if they want to play again*/
				comptotal=0; /*Sets the comptotal back to 0 for the new round*/
				playtotal=0; /*Sets the playertotal back to 0 for the new round*/
				drawchoice.erase(1,8); /*Sets drawchoice back to nothing aka sends it to the 21 equivalent of the shadow realm*/
				cin >> quit; /*User input*/
				system ("CLS"); /*Clears the screen*/
			
			}
				else if ((playtotal < 21) && (comptotal < 21) && (comptotal > playtotal)) /*If both the comp and you are under 21 but theyr have the higher total*/
			{
				cout << "You lost, your total was: " << playtotal << " which is lower than 21.\n"; /*Displays yout total*/
				cout << "The dealer's total was: " << comptotal << " which is higher than your value but lower than 21.\n"; /*Displays the comp's total*/
				loss=loss+1; /*Adds one to the loss counter*/
				cout << "Would you like to play again? [Y/N]\n"; /*Asks if they want to play again*/
				comptotal=0; /*Sets the comptotal back to 0 for the new round*/
				playtotal=0; /*Sets the playertotal back to 0 for the new round*/
				drawchoice.erase(1,8); /*Sets drawchoice back to nothing aka sends it to the 21 equivalent of the shadow realm*/
				cin >> quit; /*User input*/
				system ("CLS"); /*Clears the screen*/
			
			}
		
			
			}
			
		

	
		}
			
		cout << "You won: " <<win<< " amount of times.\n"; /*Generic tally text*/
		cout << "You lost: " <<loss<< " amount of times.\n"; /*Generic tally text*/
		cout << "Have a nice day!\n"; /*Generic text*/
			
			
			
			
	
		
	
}

	

