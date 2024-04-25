## Algoritmet dhe Strukturat e të Dhënave – Java 8


**Detyra 1:**
```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    queue<int> IntQueue;
    int shuma = 0;
    for (int i = 1; i<=10; i+=2){
        IntQueue.push (i);
    }
    
    while (!IntQueue.empty()){
        cout << "\nMadhesia e IntQueue eshte: " << IntQueue.size();
        cout << "\nNe fillim te IntQueue eshte: " << IntQueue.front();
        cout << "\nNe fund te IntQueue eshte: " << IntQueue.back();
        shuma = shuma + IntQueue.front();
        IntQueue.pop();
        }
        
        cout << "\nShuma: " << shuma;

    
    
    return 0;
}
```
**Detyra 2:**
```cpp
void paraswap(queue <char> q1,queue <char> q2) {
	for (int i = 'A';i <= 'D';i++) {
		q1.push(i);
	}
	for (int i = 'a';i <= 'd';i++) {
		q2.push(i);
	}
	cout << "Antaret e queue 1 para swap:" << endl;
	while (!q1.empty()) {
		cout << q1.front() << endl;
		q1.pop();
	}
	cout << endl << endl;
	cout << "Antaret e queue 2 para swap:" << endl;
	while (!q2.empty()) {
		cout << q2.front() << endl;
		q2.pop();
	}
	cout << endl << endl;
}
void passwap(queue <char> q1, queue <char> q2) {
	for (int i = 'A';i <= 'D';i++) {
		q1.push(i);
	}
	for (int i = 'a';i <= 'd';i++) {
		q2.push(i);
	}
	q1.swap(q2);
	cout << "Antaret e queue 1 pas swap:" << endl;
	while (!q1.empty()) {
		cout << q1.front() << endl;
		q1.pop();
	}
	cout << endl << endl;
	cout << "Antaret e queue 2 pas swap:" << endl;
	while (!q2.empty()) {
		cout << q2.front() << endl;
		q2.pop();
	}
	cout << endl << endl;
}
int main() {
	queue <char> q1;
	queue<char> q2;
	paraswap(q1,q2);
	passwap(q1, q2);
}
```
**Detyra 3:** Duke perdorur emplace() ne priority queue te tipit string, te ruhen vlerat "Kolokviumi i pare ne ASDh mbahet me 22 Prill" dhe "Kolokviumi i pare ne ASDh mbahet me 29 Prill". Ne fund, te shfaqet dhe analizohet rezultati i fituar.
