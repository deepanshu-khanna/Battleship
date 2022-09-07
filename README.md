# Battleship
Use of multidimensional array to represent a small game of battleship
#include <bits/stdc++.h>
using namespace std;
int main(){
    bool ships[4][4]{
        {0,1,1,0},
        {0,0,0,0},
        {0,0,1,0},
        {0,0,1,0}
    };
    /*Keep track of how many hits each player has and how many turns they have played, in these variables*/
    int hits=0;
    int numberofturns=0;
    /*allow the player to keep going until all four ships are hit*/
    while(hits<4){
        int row, col;
        cout<<"selecting cordinates\n";
//ask the player for a row
        cout<<"choose a row between 0-3\n";
        cin>>row;
        //ask player to choose a coloumn between 0-3
        cout<<"choose a coloumn between 0-3\n";
        cin>>col;
        //check if the ship exists between those cordinates
        if(ships[row][col]){
            /*if a ship exists in those coordinates remove it by setting it's value to 0*/
            ships[row][col]=0;
            //increase the hit counter
            hits++;
            /*tell the player he has hit a ship and how many ships are left*/
            cout<<"hit! "<<(4-hits)<<"left\n";
        }
        else{
            cout<<"miss! \n\n";
        }
        numberofturns++;
    }
    cout<<"victory \n";
    cout<<"you won in  "<<numberofturns<<"turns";
}
