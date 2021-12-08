/*****************************************
Welcome to The Football Match 5.2, a football code game in c++, by Francisco Almeida, Nuno Norte e Rodrigo Vilar.
*****************************************/

#include <iostream>
#include <cstdlib>
#include <math.h>
#include <string>
#include <stdlib.h>
#include <time.h> /* time */
#include <bits/stdc++.h>
#include <unistd.h> // usleep

using namespace std;

//variables

int goals = 0;
int shots = 3;
unsigned int microsecond = 1000000; // 1 second time
int userNumber;

double playerMove;
double cpuMove;

//strings

string userLetter;
string userName;

//functions
void header();

int level1();
int DeGea();
int Courtouis();
int Svilar();
int ShootingZone();

// Booleans
bool showHeader = true;
bool askName = true;

// Sierpinski triangle function

void printSierpinski(int n)
{
    for (int y = n - 1; y >= 0; y--) {
 
        // printing space till
        // the value of y
        for (int i = 0; i < y; i++) {
            cout<<" ";
        }
 
        // printing '*'
        for (int x = 0; x + y < n; x++) {
 
        // printing '*' at the appropriate position
        // is done by the and value of x and y
        // wherever value is 0 we have printed '*'
        if(x & y)
            cout<<" "<<" ";
        else
            cout<<"* ";
        }
 
        cout<<endl;
    }
}

void header(){
    cout <<"                                                                                                                            \n";usleep(0.5 * microsecond);//sleeps for 0.1 second
    cout <<"   ::::::::::: :::    ::: ::::::::::     :::::::::: ::::::::   :::::::: ::::::::::: :::::::::      :::     :::        :::   \n";usleep(0.5 * microsecond);//sleeps for 0.1 second     
    cout <<"      :+:     :+:    :+: :+:            :+:       :+:    :+: :+:    :+:    :+:     :+:    :+:   :+: :+:   :+:        :+:    \n";usleep(0.5 * microsecond);//sleeps for 0.1 second
    cout <<"     +:+     +:+    +:+ +:+            +:+       +:+    +:+ +:+    +:+    +:+     +:+    +:+  +:+   +:+  +:+        +:+     \n";usleep(0.5 * microsecond);//sleeps for 0.1 second
    cout <<"    +#+     +#++:++#++ +#++:++#       :#::+::#  +#+    +:+ +#+    +:+    +#+     +#++:++#+  +#++:++#++: +#+        +#+      \n";usleep(0.5 * microsecond);//sleeps for 0.1 second
    cout <<"   +#+     +#+    +#+ +#+            +#+       +#+    +#+ +#+    +#+    +#+     +#+    +#+ +#+     +#+ +#+        +#+       \n";usleep(0.5 * microsecond);//sleeps for 0.1 second
    cout <<"  #+#     #+#    #+# #+#            #+#       #+#    #+# #+#    #+#    #+#     #+#    #+# #+#     #+# #+#        #+#        \n";usleep(0.5 * microsecond);//sleeps for 0.1 second
    cout <<" ###     ###    ### ##########     ###        ########   ########     ###     #########  ###     ### ########## ##########  \n";usleep(0.5 * microsecond);//sleeps for 0.1 second
    cout <<"                                                                                                                            \n";usleep(0.5 * microsecond);//sleeps for 0.1 second
    cout <<"        :::   :::       ::: ::::::::::: ::::::::  :::    :::                                                                \n";usleep(0.5 * microsecond);//sleeps for 0.1 second
    cout <<"      :+:+: :+:+:    :+: :+:   :+:    :+:    :+: :+:    :+:                                                                 \n";usleep(0.5 * microsecond);//sleeps for 0.1 second 
    cout <<"    +:+ +:+:+ +:+  +:+   +:+  +:+    +:+        +:+    +:+                                                                  \n";usleep(0.5 * microsecond);//sleeps for 0.1 second
    cout <<"   +#+  +:+  +#+ +#++:++#++: +#+    +#+        +#++:++#++                                                                   \n";usleep(0.5 * microsecond);//sleeps for 0.1 second
    cout <<"  +#+       +#+ +#+     +#+ +#+    +#+        +#+    +#+                                                                    \n";usleep(0.5 * microsecond);//sleeps for 0.1 second
    cout <<" #+#       #+# #+#     #+# #+#    #+#        #+#    #+#                                                                     \n";usleep(0.5 * microsecond);//sleeps for 0.1 second
    cout <<"###       ### ###     ### ###     ########  ###    ###                                                                \n\n\n\n";usleep(0.5 * microsecond);//sleeps for 0.1 second
    
    
}

int main()
{

    if (showHeader == true){
        header();
        cout << "### Welcome to The Football Match 5.2 ###\n\n";
        
        if (askName == true){
        cout << "Tell us your name player!\n";
        cin >> userName;
        cout << "\nHello " << userName << " In this Match you'll shoot against goalkeepers and certainly score goals,\n"; 
        cout << "until you become a football star.\n\n";
        cout << "### shots: "<< shots <<  "\n";
        cout << "### goals: "<< goals <<  "\n\n";
        }
        else{
        cout << "\nHello " << userName << " in this Match you'll shoot against goalkeepers and certainly score goals,\n"; 
        cout << "until you become a football star.\n\n";
        cout << "### shots: "<< shots <<  "\n";
        cout << "### goals: "<< goals <<  "\n\n";
        }
    
        } else {
            cout << "\n### The Pitch\n\n";
            cout << "### shots: "<< shots <<    "\n";
            cout << "### goals: " << goals <<  "\n\n";
        }

        
        if (shots > 0){
            level1();
            
        }else{ 
            cout << "### Game Over ###\n\n";
            cin.get(); 

                       cout << "Do you want to play again\n";
            cout << "y/n\n";
            
            cin >> userLetter;
     
                if (userLetter == "y"){
                    showHeader = true;
                    askName = false;
                    main();
                }else if (userLetter == "n"){
                    cout<< "Goodbye football star " << userName << "\n\n";
                    cout << "Go on playing\n";cin.get(); 
                    return 0;
                }else{
                    return 0;
                }               
            return 0;
        } 
}

int level1(){
  cout << "You enter in a football pitch and find 3 different shooting zones\n\n";
  cout << "Choose the shooting zone 1, 2 or 3\n";
   cin >> userNumber;
   
   if(userNumber == 1){
        DeGea();
   }
   
   else if (userNumber == 2){
        Courtouis();
   }
   
   else if (userNumber == 3){
        ShootingZone();
   }
   
   else {
       main();
   }
      return 0;
}

int DeGea(){

cout <<"   .::::                        .::.::                                                   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<" .:    .::                      .::.::                                                   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<".::           .::       .::     .::.::  .::   .::       .::    .: .::     .::    .: .::: \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<".::         .::  .::  .::  .::  .::.:: .::  .:   .::  .:   .:: .:  .::  .:   .::  .::    \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<".::   .::::.::    .::.::   .::  .::.:.::   .::::: .::.::::: .::.:   .::.::::: .:: .::    \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<" .::    .:  .::  .:: .::   .::  .::.:: .:: .:        .:        .:: .:: .:         .::    \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"  .:::::      .::      .:: .:::.:::.::  .::  .::::     .::::   .::       .::::   .:::    \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"                                                               .::                       \n\n\n\n";usleep(0.1 * microsecond);//sleeps for 0.1 second

    cout << "I'm DeGea!!!\n\n";
    cout << "AhAhAh you cant't score against me\n\n";
    cout << "press p to shoot\n";
     cin >> userLetter;
     
    if (userLetter == "p"){

        cout<< "shootout\n";
        cout << "Go on playing\n";cin.get(); 
        srand (time(NULL));
        
        cpuMove = rand() %25;
        cout<< "Goalkeeper Reflexes: " << cpuMove << "\n";
        playerMove = rand() %10;
        cout<< "Player Shooting Power: " << playerMove << "\n\n";
            
            if ( playerMove > cpuMove){

cout <<"      ::::::::   ::::::::      :::     :::        ::: :::\n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"    :+:    :+: :+:    :+:   :+: :+:   :+:        :+: :+: \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"   +:+        +:+    +:+  +:+   +:+  +:+        +:+ +:+  \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"  :#:        +#+    +:+ +#++:++#++: +#+        +#+ +#+   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<" +#+   +#+# +#+    +#+ +#+     +#+ +#+        +#+ +#+    \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"#+#    #+# #+#    #+# #+#     #+# #+#                    \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"########   ########  ###     ### ########## ### ###      \n\n\n\n";usleep(0.1 * microsecond);//sleeps for 0.1 second
             cout<< "you score\n\n";
             goals += 1;
             
            cout << "### shots: "<< shots <<  "\n";
            cout << "### goals: "<< goals <<  "\n\n";
             
              cout << "Go on playing\n";cin.get(); 
              ShootingZone();
            }
            else if ( playerMove < cpuMove){
              
cout <<"       :::::::::  :::    ::: :::    ::: :::    ::: ::: :::\n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<"     :+:    :+: :+:    :+: :+:    :+: :+:    :+: :+: :+:  \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"    +:+    +:+ +:+    +:+ +:+    +:+ +:+    +:+ +:+ +:+   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<"   +#++:++#+  +#+    +:+ +#+    +:+ +#+    +:+ +#+ +#+    \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"  +#+    +#+ +#+    +#+ +#+    +#+ +#+    +#+ +#+ +#+     \n";usleep(0.1 * microsecond);//sleeps for 0.1 second     
cout <<" #+#    #+# #+#    #+# #+#    #+# #+#    #+#              \n";usleep(0.1 * microsecond);//sleeps for 0.1 second    
cout <<"#########   ########   ########   ########  ### ###       \n\n\n\n";usleep(0.1 * microsecond);//sleeps for 0.1 second  
              cout<< "you miss\n\n";  
              goals = 0;
              shots --;
              cout << "Try again\n\n";
              cout << "Go on playing\n";cin.get(); 
              showHeader = false;
              main();
              
            }
            else {  

                cout<< "rebound\n";
                cout<< "shoot again\n"; 
                cout << "Go on playing\n";cin.get(); 
                DeGea();
                
            }
        
    } else {~

        DeGea();
    }

    cout << "Go on playing\n";cin.get(); 
    return 0;  
}

int Courtouis(){
    
cout <<"   .::::                        .::.::                                                  \n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<" .:    .::                      .::.::                                                  \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<".::           .::       .::     .::.::  .::   .::       .::    .: .::     .::    .: .:::\n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<".::         .::  .::  .::  .::  .::.:: .::  .:   .::  .:   .:: .:  .::  .:   .::  .::   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<".::   .::::.::    .::.::   .::  .::.:.::   .::::: .::.::::: .::.:   .::.::::: .:: .::   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<" .::    .:  .::  .:: .::   .::  .::.:: .:: .:        .:        .:: .:: .:         .::   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"  .:::::      .::      .:: .:::.:::.::  .::  .::::     .::::   .::       .::::   .:::   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"                                                               .::                      \n\n\n\n";usleep(0.1 * microsecond);//sleeps for 0.1 second

    cout << "I'm Courtouis!!!\n\n";
    cout << "AhAhAh you cant't score against me\n\n";
    cout << "Courtouis defend all your shots until you improve your shooting power\n";
    cout << "Go on playing\n";cin.get();
    shots--;
    goals=0;

cout <<"      :::::::::  :::    ::: :::    ::: :::    ::: ::: :::\n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<"    :+:    :+: :+:    :+: :+:    :+: :+:    :+: :+: :+:  \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"    +:+    +:+ +:+    +:+ +:+    +:+ +:+    +:+ +:+ +:+  \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"   +#++:++#+  +#+    +:+ +#+    +:+ +#+    +:+ +#+ +#+   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<" +#+    +#+ +#+    +#+ +#+    +#+ +#+    +#+ +#+ +#+     \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<" #+#    #+# #+#    #+# #+#    #+# #+#    #+#             \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"#########   ########   ########   ########  ### ###      \n\n\n\n";usleep(0.1 * microsecond);//sleeps for 0.1 second

    cout << userName << " he's unstoppable\n\n";
    cout << "Go on playing\n";cin.get(); 
    
    showHeader = false;
    main();  

    return 0;
}

int ShootingZone(){

cout <<"   .::::                        .::.::                                                  \n";usleep(0.1 * microsecond);//sleeps for 0.1 second  
cout <<" .:    .::                      .::.::                                                  \n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<".::           .::       .::     .::.::  .::   .::       .::    .: .::     .::    .: .:::\n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<".::         .::  .::  .::  .::  .::.:: .::  .:   .::  .:   .:: .:  .::  .:   .::  .::   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<".::   .::::.::    .::.::   .::  .::.:.::   .::::: .::.::::: .::.:   .::.::::: .:: .::   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<" .::    .:  .::  .:: .::   .::  .::.:: .:: .:        .:        .:: .:: .:         .::   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<"  .:::::      .::      .:: .:::.:::.::  .::  .::::     .::::   .::       .::::   .:::   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<"                                                               .::                      \n\n\n\n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
  
    cout <<"In this shooting zone...\n";
    cout << "you found 3 goalkeepers\n\n";
    cout << "choose your opponent: 1, 2 or 3\n";

    cin >> userNumber;
   
   if(userNumber == 1){

        DeGea();
   }
   
   else if (userNumber == 2){

        Courtouis();
        //end of game
   }
   
   else if (userNumber == 3){

        Svilar();
   }
   
   else {
       showHeader = false;
       main();
   }
    return 0;
}

int Svilar(){

cout <<"   .::::                        .::.::                                                  \n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<" .:    .::                      .::.::                                                  \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<".::           .::       .::     .::.::  .::   .::       .::    .: .::     .::    .: .:::\n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<".::         .::  .::  .::  .::  .::.:: .::  .:   .::  .:   .:: .:  .::  .:   .::  .::   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<".::   .::::.::    .::.::   .::  .::.:.::   .::::: .::.::::: .::.:   .::.::::: .:: .::   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<" .::    .:  .::  .:: .::   .::  .::.:: .:: .:        .:        .:: .:: .:         .::   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"  .:::::      .::      .:: .:::.:::.::  .::  .::::     .::::   .::       .::::   .:::   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"                                                               .::                      \n\n\n\n";usleep(0.1 * microsecond);//sleeps for 0.1 second

    cout << "I'm Svilar the greatest goalkeeper\n";
    cout << "AhAhAh you cant't score against me\n\n";
    cout << "press p to play\n";
     
     cin >> userLetter;
     
    if (userLetter == "p"){
        
        cout<< "shootout\n\n";
        cout << "Go on playing\n";cin.get(); 
        srand (time(NULL));
        
        cpuMove = rand() %10;
        cout<< "Goalkeeper Reflexes: " << cpuMove << "\n";
        playerMove = rand() %20;
        cout<< "Player Shooting Power : " << playerMove << "\n\n";
            
            if ( playerMove > cpuMove){

cout <<"      ::::::::   ::::::::      :::     :::        ::: :::\n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<"    :+:    :+: :+:    :+:   :+: :+:   :+:        :+: :+: \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"   +:+        +:+    +:+  +:+   +:+  +:+        +:+ +:+  \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"  :#:        +#+    +:+ +#++:++#++: +#+        +#+ +#+   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<" +#+   +#+# +#+    +#+ +#+     +#+ +#+        +#+ +#+    \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"#+#    #+# #+#    #+# #+#     #+# #+#                    \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"########   ########  ###     ### ########## ### ###      \n\n\n\n";usleep(0.1 * microsecond);//sleeps for 0.1 second
            cout<< "you score\n";

            cout << "Go on playing\n";cin.get();  
            int n = 16;
            goals += 1;

            // Function calling
            printSierpinski(n);
            cout << "\n\n";
cout <<"      :::        ::::::::::     :::     :::     ::: ::::::::::     ::::::::: ::::::::::: ::::::::::: ::::::::  :::    :::\n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<"     :+:        :+:          :+: :+:   :+:     :+: :+:            :+:    :+:    :+:         :+:    :+:    :+: :+:    :+: \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"    +:+        +:+         +:+   +:+  +:+     +:+ +:+            +:+    +:+    +:+         +:+    +:+        +:+    +:+  \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"   +#+        +#++:++#   +#++:++#++: +#+     +:+ +#++:++#       +#++:++#+     +#+         +#+    +#+        +#++:++#++   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"  +#+        +#+        +#+     +#+  +#+   +#+  +#+            +#+           +#+         +#+    +#+        +#+    +#+    \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<" #+#        #+#        #+#     #+#   #+#+#+#   #+#            #+#           #+#         #+#    #+#    #+# #+#    #+#     \n";usleep(0.1 * microsecond);//sleeps for 0.1 second
cout <<"########## ########## ###     ###     ###     ##########     ###       ###########     ###     ########  ###    ###      \n\n\n\n";usleep(0.1 * microsecond);//sleeps for 0.1 second

            cout << "Go on playing\n";cin.get(); 

            cout << "\n### The Football Match ###\n\n";
            cout << "### Shoots: "<< shots <<  "\n";
            cout << "### goals: "<< goals <<  "\n\n";
            cout << userName << " you have leave the pitch,\n";
            cout << "as a Football star,\n";            
            cout << "who knows what comes ahead...\n";
            cout << "AhAhAh you cant't score against me\n\n";
            cout << "Do you want to play again\n";
            cout << "y/n\n";
            
            cin >> userLetter;
     
                if (userLetter == "y"){
                    showHeader = true;
                    askName = false;
                    main();
                }else if (userLetter == "n"){
                    cout<< "Goodbye footballer " << userName << "\n\n";
                    cout << "Go on playing\n";cin.get(); 
                    return 0;
                }else{
                    return 0;
                }               
            }
            else if ( playerMove < cpuMove){
              
cout <<"    :::::::::  :::    ::: :::    ::: :::    ::: ::: :::\n";usleep(0.1 * microsecond);//sleeps for 0.1 second  
cout <<"   :+:    :+: :+:    :+: :+:    :+: :+:    :+: :+: :+: \n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<"   +:+    +:+ +:+    +:+ +:+    +:+ +:+    +:+ +:+ +:+ \n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<"  +#++:++#+  +#+    +:+ +#+    +:+ +#+    +:+ +#+ +#+  \n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<" +#+    +#+ +#+    +#+ +#+    +#+ +#+    +#+ +#+ +#+   \n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<" #+#    #+# #+#    #+# #+#    #+# #+#    #+#           \n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
cout <<"#########   ########   ########   ########  ### ###    \n\n\n\n";usleep(0.1 * microsecond);//sleeps for 0.1 second 
             cout << "you lose the match\n\n";  
              shots--;
             cout << "Play again!\n";
              cout << "Go on playing\n";cin.get(); 
              showHeader = false;
              main();  

            }
            else {            

                cout<< "rebound\n";
                cout<< "shoot again\n";
                cout << "Go on playing\n";cin.get();  
                Svilar();               
            }        
    } 
    else {
        Svilar();

    }
    return 0;
}
