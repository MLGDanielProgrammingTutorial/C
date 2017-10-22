#include <stdio.h>
#include <stdlib.h>   //for exit(0), system("cls")
#include <conio.h>    //For kbhit, getch()
#include <time.h>     //For clock(),clock_t

int hour=0,minute=0,second=0,flag=0;     //global variables

void delay(ms)  //delay function
{
    clock_t timeDelay = ms + clock();    //Step up the difference from clock delay
    while (timeDelay > clock());         //stop when the clock is higher than time delay
}
int counter(){
    while(!kbhit() && flag ==0){     //keep looping while the user didn't hit any key and flag is 0
            if(minute > 59){            //after minute is greater than 59, reset minute and increase 1 hour
                minute = 0;++hour;
            }
                if(second > 59){         //after second is greater than 59, reset second and increase 1 minute
                    second = 0;++minute;
                    }
                     printData();           //print out the new data, delay for 1000 millisecond and increase 1 second.
                    delay(1000);second += 1;
        }
        selection();    //after the user hit the keyboard, call the menu selection
}

int printData(){   //print data to screen
system("cls");      //clear the screen
printf("1.Start  2.Stop  3.Reset  4. End\n");       //menu for user
printf("***********************************\n");
printf("            %d:%d:%d\n",hour,minute,second);      //output the data
printf("***********************************\n");
}

int selection(){      // menu selection
    switch(getch()){    //collect input from user
    case 49: flag =0; break;        //press 1 set flag to 0 means start
    case 50: flag =1; break;        //press 2 set flag to 1 means stop
    case 51:
        hour = minute = second = 0;flag = 1; //press 3 reset everything, set flag to 1 means stop
        printData();                //print the new data after reset
        break;
    case 52: exit(0);;break;        //press 4, exit the program
    }
}

int main()
{
    while(1){             //keep the program running and never end
    counter();
    }
}
