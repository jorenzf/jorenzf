#include <iostream>
#include <conio.h> 
#include <string> 
#include <stdlib.h> 
#include <ctime>

#define WRONGTRIES 5

using namespace std;

void DrawMan();
void Animal();
void Fruits();
void CpBrand();

void DrawMan(int tries){ 
	
	switch(tries){
		case 6:
		cout<<endl<<endl;
		cout<<"  -----"<<endl;
		cout<<"  |   "<<endl; 
		cout<<"  |"<<endl; 
		cout<<"  |"<<endl; 
		cout<<"  |"<<endl; 
		cout<<"  |"<<endl; 
		cout<<"__|__"<<endl;
		break;
		case 5:
		cout<<endl<<endl;
		cout<<"  -----"<<endl;
		cout<<"  |   |"<<endl; 
		cout<<"  |   "<<endl;
		cout<<"  |"<<endl; 
		cout<<"  |"<<endl; 
		cout<<"  |"<<endl; 
		cout<<"__|__"<<endl;
		break;
		case 4:
		cout<<endl<<endl;
		cout<<"  -----"<<endl;
		cout<<"  |   |"<<endl; 
		cout<<"  |   0"<<endl; 
		cout<<"  |    "<<endl; 
		cout<<"  |"<<endl; 
		cout<<"  |"<<endl; 
		cout<<"__|__"<<endl;
		break;
		case 3:
		cout<<endl<<endl;
		cout<<"  -----"<<endl;
		cout<<"  |   |"<<endl; 
		cout<<"  |   0"<<endl; 
		cout<<"  |  /|\\"<<endl; 
		cout<<"  |   "<<endl; 
		cout<<"  |"<<endl; 
		cout<<"__|__"<<endl;
		break;
		case 2:
		cout<<endl<<endl;
		cout<<"  -----"<<endl;
		cout<<"  |   |"<<endl; 
		cout<<"  |   0"<<endl; 
		cout<<"  |  /|\\"<<endl; 
		cout<<"  |   |"<<endl; 
		cout<<"  |  "<<endl; 
		cout<<"__|__"<<endl;
		break;
		case 1:
		cout<<endl<<endl;
		cout<<"  -----"<<endl;
		cout<<"  |   |"<<endl; 
		cout<<"  |   0"<<endl; 
		cout<<"  |  /|\\"<<endl; 
		cout<<"  |   |"<<endl; 
		cout<<"  |  /"<<endl; 
		cout<<"__|__"<<endl;
		break;
	default:
		cout<<endl<<endl;
		cout<<"  -----"<<endl;
		cout<<"  |   |"<<endl; 
		cout<<"  |   0"<<endl; 
		cout<<"  |  /|\\"<<endl; 
		cout<<"  |   |"<<endl; 
		cout<<"  |  / \\ "<<endl; 
		cout<<"__|__"<<endl;;
}
}


int main(){
char opt;
cout<<"----------Welcome to HANGMAN----------"<<endl;
cout<<"|                                    |"<<endl;
cout<<"|         CHOOSE A CATEGORY          |"<<endl;
cout<<"|          CHOOSE A LETTER           |"<<endl;
cout<<"|                                    |"<<endl;
cout<<"|                                    |"<<endl;
cout<<"|    1 - ANIMALS                     |"<<endl;
cout<<"|    2 - FRUTS                       |"<<endl;
cout<<"|    3 - CELLPHONE BRAND             |"<<endl;
cout<<"|                                    |"<<endl;
cout<<"|                                    |"<<endl;
cout<<"|                                    |"<<endl;
cout<<"|                                    |"<<endl;
cout<<"|                                    |"<<endl;
cout<<"--------------------------------------"<<endl;
cout<<"         SELECT:";
cin>>opt;

if(opt == '1') Animal();
else if(opt == '2') Fruits();
else if(opt == '3') CpBrand();
else{
	cout<<"Invalid output";
}
	return 0;
}

void Animal(){
	srand (time(NULL));
	system("CLS");
	string wordList[5] = {"fish","hamster","monkey","chickem","cow"}; 
	string word;
	string guessed;
	
	word = wordList[rand()%5];
	
	int wordLength = word.length();
	string dispWord (wordLength, '_'); 
	
	int found = 0;
	char guess = ' ';
	int tries = 5; //No of wrong tries
	int flagFound = 0; 

	while(tries>=0){
		system("cls");
		cout<<"-------Guess Animal Name--------"<<endl<<endl;
		 
		for(int i=0; i<wordLength; i++)
			cout<<" "<<dispWord[i]<<" "; 
		cout<<endl<<endl<<endl;
		 		
		cout<<"Wrong Attempts: "<<tries<<" / "<<WRONGTRIES<<endl;
		cout<<"Guessed Letters: "<<guessed<<endl; 
		
		DrawMan(tries);
		
		if( found == wordLength ){
			cout<<endl;
			cout<<"-----------------"<<endl;
			cout<<"|    You Win    |"<<endl;
			cout<<"-----------------"<<endl;
			break;
		}
		
		if( tries == 0) break; 
		
		cout<<"Pick a Letter:";
		guess = getche();
		
		guessed = guessed + " " + guess;
		
		if( dispWord.find(guess)!=string::npos ) tries++;
		
		flagFound = 0;
		for(int i=0; i<wordLength; i++){
			if( word[i]==guess && dispWord[i]=='_' ){
				dispWord[i] = guess;
				found++;
				flagFound = 1; 
			}
		}
		 
		if( !flagFound )
			tries--;
	}
	if( found != wordLength ){
		cout<<endl;
			cout<<"-----------------"<<endl;
			cout<<"|    You Lose    |"<<endl;
			cout<<"-----------------"<<endl;
	}
	

}

void Fruits(){
	srand (time(NULL));
	system("CLS");
	string wordList[5] = {"apple","peach","banana","strawberry","mango"};
	string word;
	string guessed;
	
	word = wordList[rand()%5];
	
	int wordLength = word.length();
	string dispWord (wordLength, '_');
	
	int found = 0;
	char guess = ' ';
	int tries = 5; //No of wrong tries
	int flagFound = 0; 

	while(tries>=0){
		system("cls");
		cout<<"-------Guess Fruit Name--------"<<endl<<endl;
		 
		for(int i=0; i<wordLength; i++)
			cout<<" "<<dispWord[i]<<" "; 
		cout<<endl<<endl<<endl;
		 		
		cout<<"Wrong Attempts: "<<tries<<" / "<<WRONGTRIES<<endl;
		cout<<"Guessed Letters: "<<guessed<<endl; 
		
		DrawMan(tries);
		
		if( found == wordLength ){
			cout<<endl;
			cout<<"-----------------"<<endl;
			cout<<"|    You Win    |"<<endl;
			cout<<"-----------------"<<endl;
			break;
		}
		
		if( tries == 0) break; 
		
		cout<<"Pick a Letter:";
		guess = getche();
		
		guessed = guessed + " " + guess;
		
		if( dispWord.find(guess)!=string::npos ) tries++;
		
		flagFound = 0;
		for(int i=0; i<wordLength; i++){
			if( word[i]==guess && dispWord[i]=='_' ){
				dispWord[i] = guess;
				found++;
				flagFound = 1; 
			}
		}
		 
		if( !flagFound )
			tries--;
	}
	if( found != wordLength ){
		cout<<endl;
			cout<<"-----------------"<<endl;
			cout<<"|    You Lose    |"<<endl;
			cout<<"-----------------"<<endl;
	}
}

void CpBrand(){
	srand (time(NULL));
	system("CLS");
	string wordList[5] = {"apple","samsung","xiaomi","oppo","myphone"};
	string word;
	string guessed;
	
	word = wordList[rand()%5];
	
	int wordLength = word.length();
	string dispWord (wordLength, '_');
	
	int found = 0;
	char guess = ' ';
	int tries = 5; //No of wrong tries
	int flagFound = 0; 

	while(tries>=0){
		system("cls");
		cout<<"-------Guess Cellphone Brands Name--------"<<endl<<endl;
		 
		for(int i=0; i<wordLength; i++)
			cout<<" "<<dispWord[i]<<" "; 
		cout<<endl<<endl<<endl;
		 		
		cout<<"Wrong Attempts: "<<tries<<" / "<<WRONGTRIES<<endl;
		cout<<"Guessed Letters: "<<guessed<<endl; 
		
		DrawMan(tries);
		
		if( found == wordLength ){
			cout<<endl;
			cout<<"-----------------"<<endl;
			cout<<"|    You Win    |"<<endl;
			cout<<"-----------------"<<endl;
			break;
		}
		
		if( tries == 0) break; 
		
		cout<<"Pick a Letter:";
		guess = getche();
		
		guessed = guessed + " " + guess;
		
		if( dispWord.find(guess)!=string::npos ) tries++;
		
		flagFound = 0;
		for(int i=0; i<wordLength; i++){
			if( word[i]==guess && dispWord[i]=='_' ){
				dispWord[i] = guess;
				found++;
				flagFound = 1; 
			}
		}
		 
		if( !flagFound )
			tries--;
	}
	if( found != wordLength ){
		cout<<endl;
			cout<<"-----------------"<<endl;
			cout<<"|    You Lose    |"<<endl;
			cout<<"-----------------"<<endl;
	}
	
	
}
