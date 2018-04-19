			/* 	THE WORD-GAME 	   */

		   /*	     HEADER FILES' INCLUSION	    */
#include<graphics.h>
#include<fstream.h>
#include<conio.h>
#include<string.h>
#include<process.h>
#include<stdio.h>
#include<dos.h>
#include<ctype.h>

		   /*	     PROTOTYPE  DECLEARATION	    */

void play();                        // To play game
int tell(int);			    // To check the repeatation of word
void selection(int);                // User's selection (logic)
void about();                       // Introduction to the game
void credit();		            // About the developer
void winner();                      // Last 5 winners
void summery(int,int);              // Summery of words entered by players
void win_update(char Winner[25]);

		/////////////////////////////////


			     /* CLASS */

			/*  FOR MAIN-MENU */

class Begin
{
  private:
	char option;

  public:
	void Menu()
	{
	   int gd=DETECT,gm;
	   initgraph(&gd,&gm,"\\TURBOC3\\BGI");
	   setbkcolor(RED);
	   setcolor(GREEN);
	   rectangle(50,100,600,300);

	      setcolor(BLUE);
	      settextstyle(GOTHIC_FONT,HORIZ_DIR,5);
		outtextxy(180,20,"MAIN-MENU");
		cout<<endl<<endl<<endl<<endl<<endl<<endl;
		settextstyle(TRIPLEX_FONT,HORIZ_DIR,2);
		setcolor(WHITE);
		outtextxy(130,120,"1 Play");
		outtextxy(130,140,"2 About");
		outtextxy(130,160,"3 Credit");
		outtextxy(130,180,"4 Winners");
		outtextxy(130,200,"5 Exit");

		settextstyle(DEFAULT_FONT,HORIZ_DIR,1);
		outtextxy(130,260,"*  Enter your choice(1-5): ");
		gotoxy(45,17);
		cin>>option;

	    selection(option);

	    clrscr();
	}

	void Choice(char a)
	{
	  int gd=DETECT,gm;
	  initgraph(&gd,&gm,"\\TURBOC3\\BGI");
	   if(a!='0')
		{
		   clrscr();
		   Menu();
		}
		else
		{
		   clrscr();
		   setbkcolor(RED);
		   cout<<"\n\tThanks for giving a look.";
		   delay(2000);
		   exit(0);
		}
	}
}Main;

		   /*    GLOBAL  VARIABLES' DECLEARATION    */

char p1[80],p2[80],word[80][80];

		   /*		THE MAIN FUNCTION	    */

void main()
{
 clrscr();

     Main.Menu();

 getch();

}

		      /* SWITCH FOR USER PREFERANCE (LOGIC) FOR MENU */

void selection(char a)
{
  int gd=DETECT,gm;
  initgraph(&gd,&gm,"\\TURBOC3\\BGI");
     do
     {
	switch(a)
	{
		case '1': play();
			break;
		case '2': about();
			break;
		case '3': credit();
			break;
		case '4': winner();
			break;
		case '5':{
			      clrscr();
			      setbkcolor(RED);
			      cout<<"\n\tThanks for giving a look.";
			      delay(2000);
			      exit(0);
			 }
			 break;
		default: {
			      clrscr();
			      setbkcolor(RED);
			      cout<<"\n\n\tSorry! It seems that you have "
				  <<"entered an incorrect key!!"
				  <<"\n\tWe should get exit...";
			      delay(4500);
			      exit(0);
			  }
	}
     }while(a!=4);
}
		       /* TO PLAY/START NEW GAME */

void play()
{
clrscr();

	int gd=DETECT,gm;
	initgraph(&gd,&gm,"\\TURBOC3\\BGI");
	setbkcolor(RED);
	setcolor(BLUE);

     int j,x,i,num=0;


	textcolor(5);

	      settextstyle(COMPLEX_FONT,HORIZ_DIR,5);
	      outtextxy(60,20,"Rules:-");
	      line(60,70,220,70);
		cout<<"\n\n\n\n\n\t\b";


	      setcolor(GREEN);
	      line(120,200,500,200);
		cout<<"\n\t1) Players must have to enter the word within "
		    <<"a fixed time-limit i.e. \n\t   30 seconds.";
		cout<<"\n\t2) One who leaves game first would be considered"
		    <<" defeated.";
		cout<<"\n\t3) Player can accept defeat by entering \'*\' "
		    <<"instead of the word.";
		cout<<"\n\t4) All words must be in small letter.";
		cout<<"\n\t\t\t\t";
		cprintf("____________________\n");
		cout<<"\n\n\n";

		cout<<"\tPress any key to proceed.";
		getch();
		clrscr();


     gd=DETECT,gm;
     initgraph(&gd,&gm,"\\TURBOC3\\BGI");
     setbkcolor(RED);

	int e,d;
		settextstyle(COMPLEX_FONT,HORIZ_DIR,3);
		outtextxy(40,20,"Let\'s Begin:-");
	      gotoxy(5,7);
		cout<<"Name of first player: ";
		gets(p1); e=strlen(p1);for(d=0;d<e;d++)p1[d]=toupper(p1[d]);
	      gotoxy(5,8);
		cout<<"Name of second player: ";
		gets(p2); e=strlen(p2);for(d=0;d<e;d++)p2[d]=toupper(p2[d]);
	      gotoxy(5,9);
		cout<<"Number of words that each player\'d enter (max 40): ";
		cin>>j;
			if((j<1)||(j>40))
			{
			  clrscr();
			  cout<<"\n\tSorry!! Wrong input. Try next time.";
			  delay(2000);
			  exit(0);
			}


		line(120,150,500,150);

		j*=2;


     gd=DETECT,gm;
     initgraph(&gd,&gm,"\\TURBOC3\\BGI");
     setbkcolor(RED);

	cout<<"\n\n\t";
	cout<<p1<<"! Enter first word: ";
	gets(word[0]);

	x=strlen(word[0]);
	   for(i=1;i<j;i++)
	   {
	      if(i%2==0)
	      { clrscr();
		gd=DETECT,gm;
		initgraph(&gd,&gm,"\\TURBOC3\\BGI");
		setbkcolor(RED);
		cout<<"\n\n\t";
		cout<<p1<<"! Enter next word starting with"
		    <<" \'"<<word[i-1][x-1]<<"\', "
		    <<"\n\t(within 30 seconds) : \t\t\t";
		gets(word[i]);

		  if((word[i][0]!=word[i-1][x-1])||(tell(i)==0))
		  {
		      do
		      {
			if(word[i][0]=='*')
			{
			  cout<<"\n\t"
			     <<"__________________________________"
			     <<"___________________________________";
			  cout<<"\n\t\t\a";
			  cout<<p2<<"! Your opponent has knelt in front"
			      <<" of you! You Won!!!";
			  goto MATCH;
			}
			else
			{
			  cout<<"\n\tWord should start with \'"
			      <<word[i-1][x-1]<<"\' & it should"
			      <<" not be repeated! \n\t";
			  cout<<"Either enter \'*\' if you have no";
			  cout<<" words, or enter the word again: ";
			  gets(word[i]);
			}

			if(word[i][0]==word[i-1][x-1])
			   break;
			num++;
		      }while(num!=2);
		  }

		    if(num==2)
		    {
			cout<<"\n\t"
			    <<"___________________________________"
			    <<"__________________________________\n";
			cout<<"\t\tSorry! "
			    <<"You\'ve crossed limit. You are lost!!";
			cout<<"\n\t\a";
			cout<<p2<<"! You won, "
			    <<"as you are a living dictionary!!";
		      goto MATCH;
		    }
		    else
		      num=0;
	      }

	      else
	      {
		cout<<"\n\n\t";
		cout<<p2<<"! Enter next word starting with"
		    <<" \'"<<word[i-1][x-1]<<"\', "
		    <<"\n\t(within 30 seconds) : \t\t\t";
		gets(word[i]);

		  if((word[i][0]!=word[i-1][x-1])||(tell(i)==0))
		  {
		      do
		      {
			if(word[i][0]=='*')
			{
			  cout<<"\n\t"
			     <<"__________________________________"
			     <<"___________________________________";
			  cout<<"\n\t\t\a";
			  cout<<p1<<"! Your opponent has knelt in front"
			      <<" of you! You Won!!!";
			  goto MATCH;
			}
			else
			{
			  cout<<"\n\tWord should start with \'"
			      <<word[i-1][x-1]<<"\' & it should"
			      <<" not be repeated! \n\t";
			  cout<<"Either enter \'*\' if you have no";
			  cout<<" words, or enter the word again: ";
			  gets(word[i]);
			}

			if(word[i][0]==word[i-1][x-1])
			   break;
			num++;
		      }while(num!=2);
		  }

		    if(num==2)
		    {
			cout<<"\n\t"
			    <<"___________________________________"
			    <<"__________________________________\n";
			cout<<"\t\tSorry! "
			    <<"You\'ve crossed limit. You are lost!!";
			cout<<"\n\t\a";
			cout<<p1<<"! You won, "
			    <<"as you are a living dictionary!!";
		      goto MATCH;
		    }
		    else
		      num=0;
	      }


	    x=strlen(word[i]);
	   }

	MATCH:
	  clrscr();

	   gd=DETECT,gm;
	   initgraph(&gd,&gm,"\\TURBOC3\\BGI");
	   setbkcolor(RED);

	   setcolor(MAGENTA);
	   settextstyle(COMPLEX_FONT,HORIZ_DIR,3);

	   rectangle(40,20,600,100);
	   if(i==j)
	   {
	      gotoxy(10,3);
	      cout<<"How great players you are! ";
	      outtextxy(100,60,"MATCH DRAW!!!");
	   }
	   else
	   {
		  if(i%2==0)
		  {
		      gotoxy(10,3);
		      cout<<"Winner is: ";
		      outtextxy(100,60,p2);
		      win_update(p2);
		  }
		  else
		  {
		      gotoxy(10,3);
		      cout<<"Winner is: ";
		      outtextxy(100,60,p1);
		      win_update(p1);
		  }
	   }

  int copy=j;
  j=i;

  char choice;

     gotoxy(13,10);
	cout<<"* Enter any key to go back to Main Menu,";
     gotoxy(15,11);
	cout<<"\'S\' for Summery  or \'0\' to get exit.";
     gotoxy(15,12);
	cout<<"Enter Your choice: ";
	cin>>choice;

	switch(choice)
	{
	  case '0': {
			clrscr();
			setbkcolor(RED);
			cout<<"\n\tThanks for giving a look.";
			delay(2000);
			exit(0);
		    }
		    break;
	  case 's': summery(j,copy);
		    break;
	  case 'S': summery(j,copy);
		    break;
	  default : {
			 clrscr();
			 Main.Menu();
		    }
	}

}

		 /*     To resist the words from being repeated    */

int tell(int i)
{
 int x=1;

 for(int j=0;j<i;j++)
 {
   if(strcmpi(word[j],word[i])==0)
   {
    x=0;
    break;
   }
 }

 return x;
}
			 /* INTRODUCTION TO WORD-GAME
			      & HOW TO PLAY  */

void about()
{
clrscr();
     char choice;

     int gd=DETECT,gm;
     initgraph(&gd,&gm,"\\TURBOC3\\BGI");
     setbkcolor(RED);
     setcolor(BLUE);

	settextstyle(TRIPLEX_FONT,HORIZ_DIR,3);
	outtextxy(40,20,"WORD-GAME");

     rectangle(40,60,620,150);
     line(40,60,40,150);
     rectangle(40,60,620,150);
     gotoxy(12,5);
	cout<<"This game is for two players, that tests your "
	    <<"vocabulary and ";
     gotoxy(10,6);
	cout<<"strengthens your command on the words of English "
	    <<"language.";
     gotoxy(12,7);
	cout<<"It would also improve your grip on this language.";
     gotoxy(12,8);
	cout<<"It has a user friendly interface, and trust "
	    <<"you would really ";
     gotoxy(10,9);
	cout<<"like this Game. It\'d be cool to call it- "
	    <<"\"ENGLISH-ANTAKSHRI\"";

	settextstyle(TRIPLEX_FONT,HORIZ_DIR,3);
	outtextxy(40,160,"HOW TO PLAY");
	rectangle(40,200,620,420);
     gotoxy(9,14);
	cout<<"1) Enter Names of the players and no. of words to be "
	    <<"entered.";
     gotoxy(9,15);
	cout<<"2) Now, one player would enter the first word.";
     gotoxy(9,16);
	cout<<"3) Then other\'d enter new word starting from last "
	    <<"word\'s last letter.";
     gotoxy(9,17);
	cout<<"4) In this way the loop would continue until players "
	    <<"would not enter ";
     gotoxy(12,18);
	cout<<"complete no. of words or anyone would not loose the game";
     gotoxy(9,19);
	cout<<"5) Every player would get 3 chances to correct his/her "
	    <<"entry.";
     gotoxy(12,21);
	cout<<"So, what are you waiting for! Come-on get your friend";
     gotoxy(12,22);
	cout<<"now and let\'s play it!!"<<endl;

     gotoxy(11,24);
	cout<<"* Enter any key to go back to Main Menu or "
	    <<"\'0\' to get exit.";
	cout<<endl;
     gotoxy(13,25);
	cout<<"Enter Your choice: ";
	cin>>choice;

	    Main.Choice(choice);
}
		      /* ABOUT THE DEVELOPER */

void credit()
{
clrscr();
     char choice;

     int gd=DETECT,gm;
     initgraph(&gd,&gm,"\\TURBOC3\\BGI");
     setbkcolor(RED);
     setcolor(BLUE);

	settextstyle(TRIPLEX_FONT,HORIZ_DIR,3);
	outtextxy(40,20,"About");

     rectangle(40,60,620,300);
     gotoxy(9,6);
	cout<<"This game is independently developed by \"Ravi Prakash\".";
     gotoxy(9,8);
	cout<<"He is currently a student of B.Sc. (Hon.) Computer Science";
     gotoxy(9,9);
	cout<<"in College of Vocational Studies (CVS) at ";
     gotoxy(9,10);
	cout<<"University of Delhi.";
     gotoxy(9,12);
	cout<<"This game is developed for submitting as a project in C++";

     gotoxy(10,15);
	cout<<"* Enter any key to go back to Main Menu or "
	    <<"\'0\' to get exit.";
     gotoxy(14,16);
	cout<<"Enter Your choice: ";
	cin>>choice;

	    Main.Choice(choice);
}
		      /* TO DISPLAY RECENT 5 WINNERS' NAME */

void winner()
{
clrscr();

     int gd=DETECT,gm;
     initgraph(&gd,&gm,"\\TURBOC3\\BGI");
     setbkcolor(RED);
     setcolor(BLUE);

	settextstyle(TRIPLEX_FONT,HORIZ_DIR,3);
	outtextxy(120,20,"Recent Winners");

     char choice;
		char ch,winners[25];
		fstream win_data;
		win_data.open("winner.txt",ios::in);
		if(!win_data)
		{  win_data.close();
		   gotoxy(18,7);
		   cout<<"File does not exist!!";
		   textcolor(14);
			cout<<endl;
		     if(choice!='0')
			{
			  clrscr();
			  Main.Menu();
			}
		     else
			{
			  clrscr();
			  setbkcolor(RED);
			  cout<<"\n\tThanks for giving a look.";
			  delay(2000);
			  exit(0);
			}
		}
		else
		{

		    rectangle(120,60,280,180);
		    int x=18,y=5;
			while(!win_data.eof())
			{
				win_data.getline(winners,25);
				win_data.get(ch);
				gotoxy(x,y);
				cout<<winners;
				y++;
			}
		}
		win_data.close();



     cout<<endl<<endl<<endl<<endl<<endl;

     gotoxy(13,13);
	cout<<"* Enter any key to go back to Main Menu or "
	    <<"\'0\' to get exit.";
     gotoxy(15,14);
	cout<<"Enter Your choice: ";
	cin>>choice;

	    Main.Choice(choice);
}
			   /* TO SUMMERISE THE GAME'S RESULT */

void summery(int j, int copy)
{
clrscr();

	int gd=DETECT,gm;
	initgraph(&gd,&gm,"\\TURBOC3\\BGI");
	setbkcolor(RED);

     cout<<"\n\n\t";
     setcolor(18);

	settextstyle(TRIPLEX_FONT,HORIZ_DIR,3);
	outtextxy(40,20,"Words entered respectivally:-");
	cout<<"\n\n";
		for(int i=0;i<j;i++)
		{
		   if(i%2==0)
		   {
		      cout<<"\tBy "<<p1<<": ";
		      puts(word[i]);
		   }
		   else
		   {
		      cout<<"\tBy "<<p2<<": ";
		      puts(word[i]);
		      cout<<"\n";
		   }
		}
	cout<<"\n\t";
     setcolor(15);
	cout<<"Result:-\n";
		if(i==copy)
		{
		   cout<<"Match Draw!!";
		   goto Place;
		}
		else
		cout<<"\n\t\t";
		cout<<"Winner is: ";
		{
		   if(i%2==0)
		      cout<<p2;
		   else
		      cout<<p1;
		}

     Place:

	cout<<"\n\n\t";
	cout<<"* Enter any key to go back to Main Menu or "
	    <<"\'0\' to get exit.\n";
	char choice;
	cout<<"\t  Enter Your choice: ";
	cin>>choice;

	    Main.Choice(choice);

}

		   /*TO UPDATE WINNER"S FILE*/

void win_update(char Winner[25])
{
	char ch,winners[25];
	int counter=1;
	fstream New("winner.txt",ios::noreplace);
	  if(New)
	   {
	     New<<Winner<<"\n";
	     New.close();
	   }
	  else
	   {
	     fstream backup("backup.txt",ios::out);
	     backup<<Winner<<"\n\t";
	     fstream old("	winner.txt",ios::in);
	     while(!old.eof())
	     {
		old.get(winners,25);
		old.get(ch);
			{   counter++;
			    backup<<winners<<"\n";
			}
		if(counter==5)
		break;
	     }
	   old.close();
	   backup.close();
		remove("winner.txt");
		rename("backup.txt","winner.txt");

	   }
}
				/* THE END */
