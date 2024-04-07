### Memoria dinamike

Shpesh nuk dimë sa hapësirë na nevojitet për shënime, psh. gjatësia e vargut.

Me operatorin `new` kërkojmë nga sistemi operativ një bllok të memories me madhësi të dëshiruar.

---

Rezultati i `new` është një **pointer** për bllokun e bajtave të alokuar në **heap**.

**Heap memoria** është memorie e procesit e cila jeton më gjatë sesa blloku i funksionit.

Zakonisht pointerët nuk na nevojiten për vlera lokale, por për vlera në heap.

---

Sintaksa: `new tipi` për një element, `new tipi[n]` për varg.
Rezultati i operacionit është pointer `tipi*`.

**Shembull:** Alokimi dinamik i një vargu:

```cpp
int n;
cout << "Sa elemente deshironi ne varg? ";
cin >> n;
int* vargu = new int[n];
// vargu[0], vargu[1], ... vargu[n - 1]
```

---

**Shembull:** Alokimi dinamik i një strukture:

```cpp
struct Drejtkendeshi { int gjeresia; int lartesia; };

Drejtkendeshi* krijo(int a, int b) {
  Drejtkendeshi* rez = new Drejtkendeshi;
  rez->gjeresia = a;
  rez->lartesia = b;
  return rez;
}

int main() {
  Drejtkendeshi* x = krijo(2, 3);
  cout << x->lartesia;
  delete x;
  return 0;
}
```

---

**Stack** quajmë memorien statike të bllokut të funksionit.

**Heap** quajmë memorien e përbashkët të procesit.
![image_java_4](https://github.com/adrianymeri/Algoritmet-dhe-Strukturat-e-Te-Dhenave-2024/assets/24792691/a0993047-9af8-4e49-9bc7-05a91c27baca)

---

Operatori `new` është i rrezikshëm pasi që memoria e alokuar nuk fshihet vetvetiu (edhe pas përfundimit të bllokut aktual).

Fshirja e memories së alokuar dinamikisht bëhet përmes `delete` (një element) dhe `delete[]` (varg).

---

**Shembull:** Alokimi dinamik për variablën `n` dhe vargun `vargu[n]`, dhe pastaj fshierja e tyre:

```cpp
int main() {
  int* n = new int;
  cout << "Sa elemente deshironi ne varg? ";
  cin >> *n;
  int* vargu = new int[*n];

  // ... kryejmë llogaritje

  // pastrojmë memorien
  delete n;
  delete[] vargu;
  return 0;
}
```

---

Disa shkurtesa për inicializim të vlerave gjatë alokimit dinamik:

```cpp
Drejtkendeshi* d1 = new Drejtkendeshi { 3, 4 };

Drejtkendeshi* d2 = new Drejtkendeshi;
*d2 = { 5, 6 };

int* x = new int { 21 };
```

**Shembull:** 
```cpp
#include <iostream>
using namespace std;

class Drejtkendeshi{
    private:
        int* gjatesia;
        int* gjeresia;
    public:
        Drejtkendeshi(int gjatesia, int gjeresia){
            // this-> gjatesia = new int (gjatesia);
            // this-> gjeresia = new int (gjeresia);
            this-> gjatesia = new int;
            (*this->gjatesia) = gjatesia;
            this-> gjeresia = new int;
            (*this->gjeresia) = gjeresia;
        }
    void showData(){
        cout << "\nGjatesia " << *gjatesia
             << "\nGjeresia " << *gjeresia;
    }
    ~Drejtkendeshi(){
        delete gjatesia;
        delete gjeresia;
    }};
int main() {
    Drejtkendeshi* d1 = new Drejtkendeshi (2,3);
    d1->showData();
    return 0;
}
```
---

**Null pointeri**

Ndonjëherë na duhet të tregojmë që pointeri nuk paraqet asnjë lokacion memorik.

Në këto raste vlera e pointerit e merr vleren 0, që zakonisht quhet `NULL`.

```cpp
int* x = NULL; // nuk ka vlerë.
```

NULL pointeri nuk mund të dereferencohet.

---

Funksionet lejohen të marrin si parametra pointerë të çfarëdoshëm.

Kur parametri është pointer, themi se po bartim shënimet përmes **referencës**.

Kur parametri nuk është pointer, themi se po bëjmë bartje përmes **vlerës** (kopjes).

---

**Shembull:** Bartja e parametrit `x` përmes vlerës:

```cpp
#include <iostream>
using namespace std;

void inkremento(int x) {
  x = x + 1;
}

int main() {
  int a = 5;
  inkremento(a);
  cout << a;
}
```

---

**Shembull:** Bartja e parametrit `x` përmes referencës:

```cpp
#include <iostream>
using namespace std;

void inkremento(int *x) {
  *x = *x + 1;
}

int main() {
  int a = 5;
  inkremento(&a);
  cout << a;
}
```

---

1. Funksionet nuk mund të kthejnë si rezultat pointer në variabla lokale.
2. Në anën tjetër, kemi të drejtë të dërgojmë pointer në variabla lokale si argument.
3. Funksionet lejohen të kthejnë pointer në heap.

Pse?

---

## Detyra shtesë

---

**Detyrë:** Të tregohet dalja në ekran për kodin në vazhdim.

```cpp
int v1[3] = { 1, 2, 3 };
int v2[3] = { 4, 5, 6 };
int *x = v1, *y = v2;
int **z = &(*x > *y ? x : y);
cout << 2 * *(*z + 1);
```

---

**Detyrë:** Të shkruhet funksioni `kopjo(v[], n)` i cili kopjon një varg dhe kthen një pointer në kopjen e vargut.

---

**Detyrë**

- Të deklarohet struktura `Drejtkendeshi`.
- Të shkruhet funksioni `lexo()`, i cili dinamikisht alokon një drejtkëndësh dhe e mbush me vlera nga tastiera.
- Në `main` të krijohet një varg prej `n` drejtkëndëshave (`n` të lexohet nga tastiera). Të mbushet vargu nga tastiera përmes funksionit `lexo`.
- Të gjendet sipërfaqja totale e të gjithë drejtkëndëshave (përmes funksionit `siperfaqja`).
- Të lirohen të gjitha resurset e alokuara.

--

```cpp
#include <iostream>
using namespace std;

struct Drejtkendeshi { int a; int b; };

Drejtkendeshi* lexo() {
  int a, b;
  cout << "Shtyp a: ";
  cin >> a;
  cout << "Shtyp b: ";
  cin >> b;
  return new Drejtkendeshi{ a, b };
}

int siperfaqja(Drejtkendeshi* d) {
  return d->a * d->b;
}

int main() {
  int n;
  cout << "Jepni numrin e drejtkendeshave: ";
  cin >> n;
  Drejtkendeshi** drejtkendeshat = new Drejtkendeshi*[n];
  for (int i = 0; i < n; i++) {
    cout << "Drejtkendeshi " << (i + 1) << endl;
    drejtkendeshat[i] = lexo();
  }

  int s = 0;
  for (int i = 0; i < n; i++) {
    s += siperfaqja(drejtkendeshat[i]);
  }

  cout << "Siperfaqja totale: " << s;

  for (int i = 0; i < n; i++) {
    // Lirimi i alokimeve individuale.
    delete drejtkendeshat[i];
  }

  // Lirimi i vargut të pointerëve.
  delete[] drejtkendeshat;
  return 0;
}
```
