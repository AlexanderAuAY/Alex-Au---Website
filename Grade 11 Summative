//Thomas Wilson & Alex Au 12/1/18
//Dev C++ 5.11
//Purpose: To make the memiest game possible	
//Data Library:		stats:		Int array that holds all of the party members' stats
//					winLoss:	Int that is used to tell if user lost or won the battle
//					exit:		Int that is set to 2 to end the program
//					prog:		Int that is used to tell which battle the player has progressed to
//					names:		String array that holds all of the names of the party members
//					end:		Int that is set to 1 to end the battle
//					i:			Int that is used as a counter
//					move:		Int array that is used to tell what move each party member used
//					target:		Int that is used to tell who a party member targeted
//					eMove:		Int that is used to tell what move the opponent used
//					eTarget:	Int that is used to tell who the opponent targeted
//					y:			Int that is used as a counter
//					death:		Int array that is used to tell if a party member is dead
//					tCheck:		Int that is used to tell if a target is dead
//					eStats:		Int array that holds all of the opponents' stats
//					damage:		Float that is used to calculate the amount of damage a party member's move did
//					eDamage:	Float that is used to calculate the amount of damage an opponent's move did
//					health:		Float that is used to tell how much health a character has left
//					eName:		String array that holds all of the opponents' names
//					mNames:		String array that holds all of the move names
//					bNames:		String array that is set to the player names so that they can be changed in battle and reset after
//					difficulty: An Int value passed over to battle function to change the stats depending on difficulty
//					leng: 		String value used with tolower to change the letters of the difficulty input and exit input for the tutorial
//					difficult:  String value used to get the difficulty setting of the player
//					toriel:		A string value used to get whether or not the user wants to see the tutorial
//					points/boosts: A combo int value to distribute and display points used by the player
//					Statnames/Playernums: Both serve to display text for the player
//					Choice:		An int used for a case statment in the tutorial

//Declares important stuff (adding libraries)
#include <iostream>
#include <windows.h>
#include <algorithm>
#include <ctime>
#include <conio.h>
#include <stdlib.h>
#include <iomanip>
#include <string.h>
#include <math.h>
#include <ctype.h>

using namespace std; //Declares important stuff

//Declares the functions for the stats screen, tutorial and the battle respectively
int MyArray (int Stats [4][5],string PlayerNames[4]); //Declares the arrays to sotre the names and stat changes of the player
void tutorial (void); //Tutorial for the game without a return value
int batMain(int stats[][5], string names[], int& prog, int& diffi), loss(); //Function used for the battle function

//Mostly coded by Alex with some by Thomas
//Main fucntion used as a hub
main()
{	
	//Declares several variables
	int difficulty,counter,leng,stats [4][5] = {{20,4,3,4,2},{30,1,7,5,3},{15,8,0,2,0},{18,0,2,5,7}},winLoss, exit = 1, prog = 0;
	string names [4], toriel, difficult;
	
	cout << "Welcome to Super Turbo Knuckles Bros 3D Land Deathmatch 2.8 HD Prologue Remix\nElectric Boogaloo All Stars Battle Royale at the Olympic Games Directors Cut\nRemastered Collection Featuring Dante from the Deval May Cry Series and KnucklesFeaturing New Funky Mode\n\n";
	cout << "Would you like to go through the tutorial? [Y/N]\n";
	cin >> toriel; //Gets the user's choice of whether or not to play the tutorial
	
	//If yes the function to display the tutorial is used
	if (toriel=="Y")
	{
		system ("CLS");
		tutorial();
	}
	
	//If no the function to display the tutorial is not used
	else if (toriel=="N")
	{
		system ("CLS");
	}
	
	//Asks the user for what difficulty they wish to play
	cout << "What difficulty would you like to play on? [Normal/Hard]\n";
	cin >> difficult; //Gets the user's choice of difficulty
	
	leng=difficult.length();
	
	//For loop that changes the user's text to lower case using the length 
	for (int counter=0; counter < leng; counter++)
	{
		//Changes the letter to lowercase
		difficult[counter]=tolower(difficult[counter]);
			
	}
	
	//If the difficulty they typed was normal
	if (difficult=="normal")
	{
		difficulty=0; //Sets a difficulty value to be passed
		system ("CLS");

	}
	
	//If the difficulty they typed was normal
	else if (difficult=="hard")
	{
		
		difficulty=1; //Sets a difficulty value to be passed
		system ("CLS");
		
	}
	
	//Text, a pause and a screen wipe
	cout << "You will now enter the game. Good luck!\n";
	Sleep(3000);
	system ("CLS");
	
	//Function to gather the stats using 2 arrays
	MyArray (stats, names);
	
	//Thomas' code starts here
	//While loop so the user can only exit if they win 
	while (exit != 2)
	{
		//Function to pass the stats, names, progress and difficulty settings of the user
		winLoss = batMain(stats, names, prog, difficulty);
		
		//If the user lost
		if (winLoss == 0)
		{
			exit = loss();
		}
		
		//If the user won
		if (prog == 5)
		{
			//Clearing screen
			system("CLS");

			cout<<"All is now Uganda";
			//Sets an exit value 
			exit = 0;
		}
	}
	
	
	
	
}

///Coded by Alex
//A fucntion for the starting stats boosts
int MyArray (int Stats [4][5],string PlayerNames[4]) //Array to carry stats and the names
{
	int counter,counter2,points=8,boosts; //Variable declaration for the counters and stats
	string Statnames[5],Playernums[4]; //String declaration for text displays
	
	//Text displays for the loops
	Statnames[0]= "HP";
	Statnames[1]= "Atk";
	Statnames[2]= "Def";
	Statnames[3]= "Mag";
	Statnames[4]= "MDef";
	
	Playernums[0]= "Deval";
	Playernums[1]= "Brudda";
	Playernums[2]= "Cammandah";
	Playernums[3]= "Quein";
	
	//For loop that ends at 4
	for (counter=0; counter < 4; counter++)
	{
		//Resets the pount values
		points=8; 
		
		//Displays the class using the array and loop
		cout << "Please enter the " <<Playernums[counter]<< " player's name: \n";
		//User input for the player's names
		cin >> PlayerNames[counter];
		
		//for loops that ends at 5
		for (counter2=0; counter2 < 5; counter2++)
		{
			//Resets the boost values
			boosts=0;
			//Shows how many point are availible to be used
			cout << "\nYou currently have "<<points<< " points to allocate\n";
			//Displays the class using the array and loop
			cout << "Please enter this person's "<<Statnames[counter2]<< " stat: \n";
			//User input for how much they want to put into a stat
			cin >> boosts;
			
			//If the boost is higher than the points availible
			if (boosts > points)
			{
				cout<< "Invalid input, the boost has been set 0\n\n";
				//Resets value
				boosts=0;
				
			}
			
			//If the boost is lower or equal than the points availible
			else if (boosts <= points)
			{
				//Subtracts points avaible from the boosts
				points= points-boosts;
			
			}
			
			//Adds the boosts on the stats using the loops and arrays
			Stats[counter][counter2]=Stats[counter][counter2]+boosts;
		
		}
		
		//Screen wipe
		Sleep(1000);
		system ("CLS");

	}

}

//Coded by Alex
//Void since it's a display
void tutorial (void)
{
	//Sets variables for the case statment, loop and string manipulation
	int choice,counterfunc1,leng;
	//Sets the variable for the while loop
	string quit="yes";
	
	//While the user doesn't want to quit
	while (quit!="no")
	{
		
	//Text displays
	cout << "What aspects of the game would you like to read about?\n";
	cout << "1. Characters\n2. Battle system\n3. Win/loss scenarios\n";
	cout << "Please make you choice using the numbers: "; 
	//The user's choice
	cin >> choice;
	
	//Switch statement to show the text depending on the user's input
	switch (choice)
	{
		//If the user input 1
		case (1):
			system ("CLS");
			cout << "The characters are as follows:\n";
			cout << "The Deval is a mixed attacker with lower defenses\nThe Brudda has high Def with great Mag and low Atk and MDef\nThe Cammandah has high Atk and low defenses\nFinally the Quein has high Mag and MDef but lower Def and MDef\n";
			break;
		
		//If the user input 1
		case (2):
			system ("CLS");
			cout << "The battle system features 3 basic commands based off of 4 stats.\nAttack is used to attack and the damage is based off of your attack stat and theopponent's Def.\nThe same applies to you as well, and the system is simlarly used with Mag and MDef and the Magic Attack command.\nDefend is used to halve damage both physical and magical.\n";
			break;
		
		//If the user input 1
		case (3):
			system ("CLS");
			cout << "When all your party members have died, you lose and its a game over.\nIf you win however, you are granted a stat boost along with additional stats.\n";
			break;
		

	}
	
	//Text display
	cout << "Do you require another explanantion?\n";
	//Gets the user's choice to quit or stay
	cin >> quit;
	
	//Gets theit input length
	leng=quit.length();
		
		//For loop that changes the user's text to lower case using the length 
		for (int counterfunc1=0; counterfunc1 < leng; counterfunc1++)
		{
			//Changes the letter to lowercase
			quit[counterfunc1]=tolower(quit[counterfunc1]);
			
		}
		
		//Screen wipe
		system ("CLS");

	
	}
	
	//Screen wipe
	system ("CLS");
	
}

//making a function for the battles (Mostly Thomas, some Alex)
int batMain(int stats[][5], string names[], int& prog, int& diffi)
{
	//declaring variables
	int winLoss, counter,counter2,counter3,counter4,boosts, points, end = 0, i, move[4], target[4], eMove, eTarget, y, x, death[4] = {0, 0, 0, 0}, tCheck,eStats[5][5]={{50,17,3,15,3},{100,25,1,25,1},{150,20,25,30,20},{300,30,45,1,45},{250,50,45,50,45}};
	float damage[4] = {0,0,0,0}, eDamage = 0, health[5];
	string eName[5] = {"Dad", "Jake Paul", "Logan Paul", "Donald Trump", "Kim Jong Un"}, Statnames[5], mNames[3] = {"spit", "magic ov za deval", "defend"}, bNames[4];
	
	//Alex coding starts
	
	//if user chose hard difficulty
	if (diffi==1)
	{
		//loops 5 times (0 to 4)
		for (counter3=0; counter3 < 5; counter3++)
		{
			//loops 5 times (0 to 4)
			for (counter4=0; counter4 < 5; counter4++)
			{
				//multiplying opponent stats by 2
				eStats[counter3][counter4]=eStats[counter3][counter4]*2;	
			}		
		}
	}
	
	//naming the stats
	Statnames[0]= "HP";
	Statnames[1]= "Atk";
	Statnames[2]= "Def";
	Statnames[3]= "Mag";
	Statnames[4]= "MDef";
	
	//Alex coding ends
	
	//for loop that loops 4 times (0 to 3)
	for (i = 0; i < 4; i++)
	{
		//setting party member health to what is in party member stats
		health[i] = stats[i][0];
		//setting battle name to name
		bNames[i] = names[i];
	}
	//setting opponent health to what is opponent stats
	health[4] = eStats[prog][0];
	
	//exits when player losses or wins
	while (end != 1)
	{
		//for loop that loops 4 times (0 to 3)
		for (i = 0; i <= 3; i++)
		{
			//Clearing screen
			system("CLS");
			
			//setting the move to nothing
			move[i] = 0;
			
			//if the party member is not dead
			if (death[i] != 1)
			{
				//loops 4 times (0 to 3)
				for (y = 0; y < 4; y++)
				{
					//Displaying party member health
					cout<<bNames[y]<<": "<<health[y]<<" HP\n";
				}
				//displaying opponent health
				cout<<eName[prog]<<": "<<health[4]<<" HP\n\n";
				
				//finding out what move the user wants to use
				cout<<"What would you like "<<bNames[i]<<" to do?";
				cout<<"\nSpit (1) \nMagic ov za Deval (2) \nDefend(3) \n\n";
				cin>>move[i];
				
				//if the user chose to heal
				if ((i == 3) && (move[3] == 2))
				{
					//finding out who the player would like to heal
					cout<<"\n\nWho would you like to heal?";
					for (x = 0; x <= 3; x++)
					{
						cout<<"\n"<<bNames[x]<<" ("<<x + 1<<")";
					}
					cout<<"\n\n";
					cin>>target[i];
					target[i] = target[i] - 1;
				}
				//if the user didn't chose to defend
				else if (move[i] != 3)
				{
					//setting the target to the opponent
					target[i] = 5;
				}
				//if the player chose to defend
				else if (move[i] == 3)
				{
					//setting the target to no one
					target[i] = 4;
				}
			}
		}
		
		//randomly choosing the oponents moves
		eMove = (rand()%3);
		
		//setting tCheck to 1
		tCheck = 1;
		
		//exits once the opponent targets a party member that isn't dead
		while (tCheck != 0)
		{
			//randomly choosing the opponent's target
			eTarget = (rand()%4);
			//if the target is not dead
			if (death[eTarget] != 1)
			{
				//setting tCheck to 0
				tCheck = 0;
			}
		}
		
		//Clearing screen
		system("CLS");
		
		//loops 4 times (0 to 3)
		for (i = 0; i <= 3; i++)
		{
			//if party member used spit
			if ((target[i] == 5)&&(move[i] == 1))
			{
				//calculating the damage
				damage[i] = stats[i][1] - eStats[prog][2];
				
				//if damage is less than 0
				if (damage[i] < 0)
				{
					//setting damage to 0
					damage[i] = 0;
				}
				//if opponent chose to defend
				else if (eMove == 2)
				{
					//damage is halved
					damage[i] = damage[i] / 2;
				}
			}
			//if party member used magic ov za deval
			else if ((target[i] == 5)&&(move[i] == 2))
			{
				//calculating the damage
				damage[i] = stats[i][3] - eStats[prog][2];
				
				//if damage is less than 0
				if (damage[i] < 0)
				{
					//setting damage to 0
					damage[i] = 0;
				}
				//if opponent chose to defend
				else if (eMove == 2)
				{
					//damage is halved
					damage[i] = damage[i] / 2;
				}
			}
			//if the party member used defend
			else if (move[i] == 3)
			{
				//setting damage to 0
				damage[i] = 0;
			}
		}
		
		//if opponent chose spit
		if (eMove == 0)
		{
			//calculating damage
			eDamage = eStats[prog][1] - stats[eTarget][2];
			
			//if damage is less than 0
			if (eDamage < 0)
			{
				//setting damage to 0
				eDamage = 0;
			}
			//if target chose defend
			else if (move[eTarget] == 3)
			{
				//damage is halved
				eDamage = eDamage / 2;
			}
		}
	//if opponent chose magic ov za deval
		else if (eMove == 1)
		{
			//calculating damage
			eDamage = eStats[prog][3] - stats[eTarget][2];
			
			//if damage is less than 0
			if (eDamage < 0)
			{
				//setting damage to 0
				eDamage = 0;
			}
			//if target chose defend
			else if (move[eTarget] == 3)
			{
				//damage is halved
				eDamage = eDamage / 2;
			}
		}
		//if opponent chose defend
		else if (eMove == 2)
		{
			//setting damage to 0
			eDamage = 0;
		}
		
		//loops 4 times (0 t0 3)
		for (i = 0; i <= 3; i++)
		{
			//subtracting party member's damage from opponent's health
			health[4] = health[4] - damage[i];
		}
		
		//subtracting opponent's damage from target's health
		health[eTarget] = health[eTarget] - eDamage;
		
		//if player chose to heal
		if (move[3] == 2)
		{
			//adding to target's health
			health[target[3]] = health[target[3]] + stats[3][3];
			
			//if target's health went over max
			if (health[target[3]] > stats[target[3]][0])
			{
				//setting target's health to the max
				health[target[3]] = stats[target[3]][0];
			}
			
			//if the target is dead
			if (death[target[3]] == 1)
			{
				//setting target's health back to 0
				health[target[3]] = 0;
			}
		}
		
		//loops 4 times (0 to 3)
		for (i = 0; i <= 3; i++)
		{
			//if party member is not dead
			if (death[i] != 1)
			{
				//displaying what move they used
				cout<<bNames[i]<<" used "<<mNames[move[i] - 1];
				//if party member targeted opponent
				if (target[i] == 5)
				{
					//displaying damage done and who they targetted
					cout<<" on "<<eName[prog]<<" for "<<damage[i]<<" damage";
				}
				//if party member used heal
				else if (move [i] == 2)
				{
					//displaying who party member targetted
					cout<<" on "<<bNames[target[i]];
				}
				
				//moving screen down
				cout<<"\n";
				
				//if health is less than or equal to 0
				if (health[i] <= 0)
				{
					//setting health to 0
					health[i] = 0;
					//setting death[i] to 1 to let program know party member is dead
					death[i] = 1;
					//adding (Dead) at the end of their name
					bNames[i] = bNames[i].append(" (Dead)");
				}
			}
		}
		
		//displaying what move opponent used
		cout<<eName[prog]<<" used "<<mNames[eMove];
		//if opponent did not defend
		if (eMove != 2)
		{
			//displaying who they targetted and how much damage they did
			cout<<" on "<<bNames[eTarget]<<" for "<<eDamage<<" damage";
		}
		
		//moving screen down
		cout<<"\n\n";
		
		//pausing screen
		system("PAUSE");
		
		//if opponent's health is less than or equal to 0
		if (health[4] <= 0)
		{
			//setting winLoss to 1
			winLoss = 1;
			//setting end to 1
			end = 1;
			//adding 1 to prog
			prog = prog + 1;
			
			//Clearing screen
			system("CLS");
			
			//outputting to user that they won
			cout<<eName[prog - 1]<<" succumbed to the power of the deval\n\n";
			
			//Alex coding starts
			
			//telling user they will now level up party members
			cout<< "You will now be taken to the level up screen\n";
			Sleep(1000);
			
			//Clearing screen
			system ("CLS");
			
			//loops 4 times (0 to 3)
			for (counter=0; counter < 4; counter++)
			{
				//setting available points to 8
				points=8;
				
				//loops 5 times (0 to 4)
				for (counter2=0; counter2 < 5; counter2++)
				{
					//setting stat boost to 0
					boosts=0;
					//displaying amount of points left
					cout << "You currently have "<<points<< " points to allocate\n";
					//finding out how many points user wants to add to a stat
					cout << "Please enter "<<names[counter]<<"'s "<<Statnames[counter2]<< " stat boost: \n";
					cin >> boosts;
					
					//if user uses more points than are remaining
					if (boosts > points)
					{
						//telling user input was invalid and boost has been set to 0
						cout<< "Invalid input, the boost has been set 0\n\n";
						//setting boost to 0
						boosts=0;				
					}
					//if user doesn't use more points than are remaining
					else if (boosts <= points)
					{
						//subtracting points used from points remaining
						points= points-boosts;
					}
					
					//adding boosts to stats
					stats[counter][counter2]=stats[counter][counter2]+boosts;		
				}
				
				//pausing screen
				Sleep(1000);
				
				//clearing screen
				system ("CLS");
			}
			
			//pausing screen
			system("PAUSE");
			
			//Alex coding ends
		}
		//if all party members died
		else if((death[0] == 1)&&(death[1] == 1)&&(death[2] == 1)&&(death[3] == 1))
		{
			//setting winLoss to 0
			winLoss = 0;
			//seting end to 1
			end = 1;
		}
	}
	
	//returning winLoss
	return winLoss;
}

int loss()
{
	//declaring variables
	int exit, leave = 1;
	
	while (leave != 0)
	{
		//Clearing screen
		system("CLS");
		
		//outputting to user that they lost
		cout<<"Uganda has been defeated\n";
		
		//finding out if user would like to retry the battle or quit
		cout<<"Would you like to retry the battle (1) or quit the game (2)?: ";
		cin>>exit;
		
		if ((exit == 1)||(exit == 2))
		{
			leave = 0;
		}
	}
	//returning exit
	return exit;
}


