#include <fstream>
#include <iostream>
#include <iomanip>
#include <string>
#include <cstdlib>

using namespace std;

int NRANGE = 0;
int SRANGE = 0;
int NROW = 0;
int SROW = 0;

void Select(string type);

void InitArr(int *A, int SIZE);

void NormalNumber(int x, int *N);

void SpecialNumber(int x, int *S);

void PrintStatistic(int *N, int *S);

void Rank(int *N, int *S);

void Select(string type){
	if(type == "ht"){
		NRANGE = 48; //47 + 1
		SRANGE = 20; //19 + 1
		NROW = (NRANGE / 5) + 1;
		SROW = (SRANGE / 5) + 1;
	}
	else if(type == "lfl"){
		NRANGE = 49; //48 + 1
		SRANGE = 19; //18 + 1
		NROW = (NRANGE / 5) + 1;
		SROW = (SRANGE / 5) + 1;
	}
	else if(type == "mm"){
		NRANGE = 76; //75 + 1
		SRANGE = 16; //15 + 1
		NROW = (NRANGE / 5) + 1;
		SROW = (SRANGE / 5) + 1;
	}
	else if(type == "pb"){
		NRANGE = 70; //69 + 1
		SRANGE = 27; //26 + 1
		NROW = (NRANGE / 5) + 1;
		SROW = (SRANGE / 5) + 1;
	}
	else{
		cout << "The type of lottery you entered is not supported";
		exit(2);
	}
}

void InitArr(int *A, int SIZE){
	for(int i = 0; i < SIZE; i++){
		A[i] = 0;
	}
}

void NormalNumber(int x, int *N){
	for(int i = 1; i < NRANGE; i++){
		if(x == i){
			N[i] += 1;
		}
	}
}

void SpecialNumber(int x, int *S){
	for(int i = 1; i < SRANGE; i++){
		if(x == i){
			S[i] += 1;
		}
	}
}

void PrintStatistic(int *N, int *S){
	cout << "Numb:Time" << endl;
	cout << "--------------Normal Number--------------" << endl;
	for(int i = 1; i < NRANGE; i++){
		cout << setw(4) << i << ":" << N[i];
		if(i % 5 == 0){
			cout << endl;
		}
	}
	cout << endl;
	cout << "--------------Special Number--------------" << endl;
	for(int i = 1; i < SRANGE; i++){
		cout << setw(4) << i << ":" << N[i];
		if(i % 5 == 0){
			cout << endl;
		}
	}
}

void Rank(int *N, int *S){
	
}

int main(){
	string type;
	cout << "ht = Hot Lottp, lfl = Lucky For Life, mm = Mega Millions, pb = Power Ball" << endl;
	cout << "select type of lottery:";
	cin >> type;
	Select(type);
	int a, b, c, d, e, f;
	int N[NRANGE];
	InitArr(N, NRANGE);
	int S[SRANGE];
	InitArr(S, SRANGE);
	string dump;
	ifstream ifin;
	string name;
	cout << "Enter file name to load. (e.g. pb.txt)" << endl;
	cin >> name;
	ifin.open(name.c_str());
	if(ifin.fail()){
		cout << "fail to open";
	}
	while(!ifin.eof()){
		ifin >> dump >> a >> b >> c >> d >> e >> f >> dump >> dump;
		NormalNumber(a, N);
		NormalNumber(b, N);
		NormalNumber(c, N);
		NormalNumber(d, N);
		NormalNumber(e, N);
		SpecialNumber(f, S);
	}
	PrintStatistic(N, S);
}
