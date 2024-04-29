## Përsëritje

---

Memoria është një varg bajtash ku ruhen shënime.

Secili bajt i memories ka një adresë unike.
![img2](https://github.com/adrianymeri/Algoritmet-dhe-Strukturat-e-Te-Dhenave-2024/assets/24792691/1c55c317-a494-43df-8f8c-4209b8260cea)


---

Zakonisht ne nuk i qasemi direkt vlerave në memorie.

Qasjen në të dhëna e bëjmë përmes **variablave**.

Kompajlleri kujdeset për shndërrimet e nevojshme.

---

Variabla është emërtim për një hapësirë memorike.

```cpp
int x = 5;
int y = 3;
int z = -2;
```
![img1](https://github.com/adrianymeri/Algoritmet-dhe-Strukturat-e-Te-Dhenave-2024/assets/24792691/245c9a61-f2df-453d-8186-844196d40675)

---

Variablat lokale alokohen në memorien e funksionit aktual – stack memoria.

Ato nuk shihen nga jashtë, si dhe humbasin në momentin qe mbyllet blloku i funksionit (stack frame).

Variablat lokale janë adresa memorike në një distancë fikse ndaj stack pointerit aktual.

---

## Pointerët dhe referencat

---

**Pointerët** janë variabla të tipit integer të cilat mbajnë një adresë.
Zakonisht në atë adresë ruhet ndonjë vlerë e tipit të caktuar, psh. `int`, `double`, etj.

Deklarimi i pointerit: `tipi* emri`.

Kodi në vazhdim i deklaron dy pointerë `x` dhe `y`.

```cpp
int* x;
double* y;
```

---

Pointeri është thjeshtë një variabël numerike që mban një adresë (32-bit ose 64-bit).

Kjo vlerë mund t'i nënshtrohet llogaritjeve aritmetikore si çdo integer tjetër.

```cpp
int* x;
x = 4; // sa për demonstrim
int* y;
y = x + 1; // merr vlerën 5
```

---

Nëse kemi një pointer `x` atëherë:

- Shprehja `x` e jep vlerën pointerit `x` (adresën).
- Shprehja `*x` e jep vlerën që gjendet në adresën `x`.

Operatori `*x` për cilindo pointer `x` njihet si **operator i dereferencimit**.

---

Është dhënë memoria në vazhdim si dhe pointeri `x` i cili ka vlerën 3.

![img3](https://github.com/adrianymeri/Algoritmet-dhe-Strukturat-e-Te-Dhenave-2024/assets/24792691/f251f854-9344-493a-907f-15556b29a894)

---

Vargu është pointer që tregon adresën e elementit të parë në rendin e elementeve.

```cpp
int vargu[5] = { 8, 2, 5, 7, 6 };
cout << *vargu;       // shfaqet 8
cout << *(vargu + 3); // shfaqet 7
cout << vargu[3];     // shfaqet 7
```
![img4](https://github.com/adrianymeri/Algoritmet-dhe-Strukturat-e-Te-Dhenave-2024/assets/24792691/54b21ec0-e28b-4ab8-8215-495ae2eceb49)

---

Nëse kemi një pointer `v`, psh. në një varg.

```cpp
int v[5] = { 3, 2, 1, 5, 6 };
```

Shprehjet `v[i]` dhe `*(v+i)` janë ekuivalente.

Shprehjet `v[0]`, `*v`, `*(v+0)` janë ekuivalente.

---

**Detyrë:** Të tregohet dalja në ekran për kodin në vazhdim.

```cpp
int vargu[4] = { 2, 1, 0, 5 };
int s = 0;
for (int i = 0; i < 4; i++) {
  s += *(vargu + i);
}

cout << s;
```

---

**Detyrë:** Të tregohet dalja në ekran për kodin në vazhdim.

```cpp
int vargu[4] = { 3, 7, 1, -2 };
int* ptr1 = vargu + 1;
int* ptr2 = vargu + 3;
cout << *ptr1 + *(ptr2 - 1);
```

**Kujdes:** Ylli (`*`) gjatë deklarimit ka kuptim tjetër prej yllit gjatë dereferencimit.

---

**L-Values**

Rikujtim: Cilado shprehje që mund të paraqitet në anën e majtë të shoqërimit (`=`) quhet l-value.

Vlerat numerike dhe rezultatet e llogaritjeve nuk mund të paraqiten në anën e majtë:

```cpp
2 + 3 = a; // gabim
```

---

**Operatori &**

Përmes operatorit `&` mund t'ia marrim adresën e një l-value.
Ky operator kthen një pointer për adresën memorike ku gjendet shprehja.

```cpp
int a = 5;
int* ptr = &a;
cout << *ptr; // shfaqet 5
```

---

**Përmbledhje – pointerët**

Deklarimi `int* x = &a` tregon që kemi një pointer `x` për një shënim `a` të tipit `int`.

Shprehja `x` tregon adresën ku gjendet shënimi `a`.

Shprehja `*x` tregon vlerën që gjendet në atë adresë, dmth. vlerën e shënimit `a`.

---

**Detyrë:** Të tregohet dalja në ekran për kodin në vazhdim.

```cpp
int a = 5;
int b = 8;
int* x = &a;
int* y = ((*x) % 2 == 0) ? (&a) : (&b);
cout << *x + *y;
```

---

**Detyrë:** Të tregohet dalja në ekran për kodin në vazhdim.

```cpp
int a = 4;
int b = *(&a);
cout << b;
```

---

**Detyrë:** Të tregohet dalja në ekran për kodin në vazhdim.

```cpp
double v[5] = { -2, 5.3, 3, 1, 2.2 };
double* ptr = v + 1;
cout << ptr[0] + ptr[2];
```

---

**Detyrë:** Të tregohet dalja në ekran për kodin në vazhdim.

```cpp
int v[5] = { -2, 5, 3, 1, 2 };
int* ptr = v + 2;
int* a = &ptr[-1];
int* b = &v[3];
(*a)++;
*b = ptr[-2];
cout << v[0] + v[1] + v[2] + v[3] + v[4];
```

---

**Detyrë:** Të tregohet dalja në ekran për kodin në vazhdim.

```cpp
int v[5] = { -2, 5, 3, 1, 2 };
int* ptr = v;
int a = *(ptr++);
int b = *ptr;
cout << a + b;
```

---

**Detyrë:** Të tregohet dalja në ekran për kodin në vazhdim.

```cpp
int a = 1, b = 2, c = 3;
int *x = &a, *y = &b, *z = &c;
y = z;
z = x;
x = y;
cout << *x << ", " << *y << ", " << *z;
```

---

**Detyrë:** Të tregohet dalja në ekran për kodin në vazhdim.

```cpp
int a = 1, b = 2, c = 3;
int *x = &a, *y = &b, *z = &c;
int* v[3] = { x, y, z };
cout << *(v[1]); // **(v + 1)
```

---

**Detyrë:** Të tregohet dalja në ekran për kodin në vazhdim.

```cpp
int a = 4, b = 5;
int *x = &a, *y = &b;
int** ptr = (a > b) ? (&x) : (&y);
cout << **ptr;
```

---

**Detyrë:** Të shkruhet funksioni i cili e llogarit shumën e vargut të numrave me presje dhjetore.
Parametri i vargut të shkruhet si pointer.

---

**Pointerët në struktura**

Pointerët mund të adresojnë edhe tipe komplekse.

Qasja në anëtarët bëhet përmes operatorit `->`.

```cpp
struct Drejtkendeshi { int gjeresia; int lartesia; };

int main() {
  Drejtkendeshi a = { 3, 4 };
  Drejtkendeshi* ptr = &a;
  cout << "Gjeresia: " << (*ptr).gjeresia << endl;
  cout << "Lartesia: " << ptr->lartesia << endl;
  return 0;
}
```

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
  return new Drejtkendeshi { a, b };
}

int siperfaqja(Drejtkendeshi *d) {
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
---
