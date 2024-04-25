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
