## Algoritmet dhe Strukturat e të Dhënave – Java 6

---

## Arrays - STL
**Detyra 1:** Perdorimi i disa metodave qe ofron libraria <array>
```cpp
#include <iostream>
#include <array>
#include <iterator>
#include <algorithm> 
using namespace std;

int main() {
    array <int,5> arr1{{2,1,4,3,5}};
    array <int,5> arr2 = {1,2,3,4,5};
    array <char,2> arr3 = {'Y','X'};
    array <string,2> arr4 = {"B","A"};
    
    stack<int>Steku;
    
    cout << "Anetaret e arr1: \n";
    for (auto i : arr1){
        cout << i << " ";
    }
    
    cout << "\nAnetaret e arr2: \n";
    for (auto i : arr2){
        cout << i << " ";
    }
    
    cout << "\nAnetaret e arr3: \n";
        for (auto i : arr3){
            cout << i << " ";
    }
    
    cout << "\nAnetaret e arr4: \n";
        for (auto i : arr4){
            cout << i << " ";
    }
    
    sort(arr1.begin(),arr1.end());
    sort(arr2.begin(),arr2.end());
    sort(arr3.begin(),arr3.end());
    sort(arr4.begin(),arr4.end());

    
    cout << "\n\n\nAnetaret e arr1 pas sortimit: \n";
    for (auto i : arr1){
        cout << i << " ";
    }
    
    cout << "\nAnetaret e arr2 pas sortimit: \n";
    for (auto i : arr2){
        cout << i << " ";
    }
    
    cout << "\nAnetaret e arr3 pas sortimit: \n";
        for (auto i : arr3){
            cout << i << " ";
    }
    
    cout << "\nAnetaret e arr4 pas sortimit: \n";
        for (auto i : arr4){
            cout << i << " ";
    }
    
    cout << "---------------------------------------";
    
    arr1.fill(0);
    cout << "\n\n\nAnetaret e arr1 pas fill: \n";
    for (auto i : arr1){
        cout << i << " ";
    }
    
    cout << "\nGjatesia e arr2 eshte:" << arr2.size();
    
    arr1.swap(arr2);
    
    cout << "\n\n\nAnetaret e arr1 pas swap: \n";
    for (auto i : arr1){
        cout << i << " ";
    }
    
    cout << "\nAnetaret e arr2 pas swap: \n";
    for (auto i : arr2){
        cout << i << " ";
    }
    
    cout << "\nAnetari i pare i arr1: " << arr1.front();
    cout << "\nAnetari i pare i arr3: " << arr3.front();
    cout << "\nAnetari i fundit i arr2: " << arr2.back();
    cout << "\nAnetari i fundit i arr4: " << arr3.back();

    return 0;
}
```
**Detyra 2:** Hyrje ne Stack
```cpp
#include <iostream>
#include <array>
#include <iterator>
#include <algorithm> 
using namespace std;

int main() {
    array <int,5> arr1{{2,1,4,3,5}};
    array <int,5> arr2 = {1,2,3,4,5};
    array <char,2> arr3 = {'Y','X'};
    array <string,2> arr4 = {"B","A"};
    
    stack<int>Steku;
    
    cout << "Anetaret e arr1: \n";
    for (auto i : arr1){
        cout << i << " ";
    }
    
    cout << "\nAnetaret e arr2: \n";
    for (auto i : arr2){
        cout << i << " ";
    }
    
    cout << "\nAnetaret e arr3: \n";
        for (auto i : arr3){
            cout << i << " ";
    }
    
    cout << "\nAnetaret e arr4: \n";
        for (auto i : arr4){
            cout << i << " ";
    }
    
    sort(arr1.begin(),arr1.end());
    sort(arr2.begin(),arr2.end());
    sort(arr3.begin(),arr3.end());
    sort(arr4.begin(),arr4.end());

    
    cout << "\n\n\nAnetaret e arr1 pas sortimit: \n";
    for (auto i : arr1){
        cout << i << " ";
    }
    
    cout << "\nAnetaret e arr2 pas sortimit: \n";
    for (auto i : arr2){
        cout << i << " ";
    }
    
    cout << "\nAnetaret e arr3 pas sortimit: \n";
        for (auto i : arr3){
            cout << i << " ";
    }
    
    cout << "\nAnetaret e arr4 pas sortimit: \n";
        for (auto i : arr4){
            cout << i << " ";
    }
    
    cout << "---------------------------------------";
    
    arr1.fill(0);
    cout << "\n\n\nAnetaret e arr1 pas fill: \n";
    for (auto i : arr1){
        cout << i << " ";
    }
    
    cout << "\nGjatesia e arr2 eshte:" << arr2.size();
    
    arr1.swap(arr2);
    
    cout << "\n\n\nAnetaret e arr1 pas swap: \n";
    for (auto i : arr1){
        cout << i << " ";
    }
    
    cout << "\nAnetaret e arr2 pas swap: \n";
    for (auto i : arr2){
        cout << i << " ";
    }
    
    cout << "\nAnetari i pare i arr1: " << arr1.front();
    cout << "\nAnetari i pare i arr3: " << arr3.front();
    cout << "\nAnetari i fundit i arr2: " << arr2.back();
    cout << "\nAnetari i fundit i arr4: " << arr3.back();

    return 0;
}
```
