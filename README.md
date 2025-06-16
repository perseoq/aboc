
# **Manual Completo de Aritmética en C++**

Este manual cubre todos los temas fundamentales de aritmética implementados en C++, con ejemplos prácticos y explicaciones detalladas.

---

## **1. Operaciones Básicas**
Las operaciones básicas en C++ son suma (`+`), resta (`-`), multiplicación (`*`) y división (`/`).

### **Ejemplo:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10, b = 5;
    
    cout << "Suma: " << a + b << endl;       // 15
    cout << "Resta: " << a - b << endl;      // 5
    cout << "Multiplicación: " << a * b << endl; // 50
    cout << "División: " << a / b << endl;   // 2 (división entera)
    
    double c = 10.0, d = 3.0;
    cout << "División decimal: " << c / d << endl; // 3.33333
    
    return 0;
}
```

---

## **2. Valor Posicional (Sistema Decimal)**
El valor posicional indica el valor de un dígito según su posición en un número.

### **Ejemplo: Descomposición de un número**
```cpp
#include <iostream>
using namespace std;

int main() {
    int num = 3456;
    int unidades = num % 10;          // 6
    int decenas = (num / 10) % 10;    // 5
    int centenas = (num / 100) % 10;  // 4
    int millares = num / 1000;        // 3

    cout << "Millares: " << millares << endl;
    cout << "Centenas: " << centenas << endl;
    cout << "Decenas: " << decenas << endl;
    cout << "Unidades: " << unidades << endl;

    return 0;
}
```

---

## **3. Números Naturales**
Los números naturales (`ℕ`) son enteros positivos (`1, 2, 3, ...`).

### **Ejemplo: Suma de los primeros N números naturales**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n = 10;
    int suma = n * (n + 1) / 2; // Fórmula de Gauss
    
    cout << "Suma de los primeros " << n << " naturales: " << suma << endl; // 55
    
    return 0;
}
```

---

## **4. Números Enteros (Incluyendo Negativos)**
Los números enteros (`ℤ`) incluyen positivos, negativos y cero.

### **Ejemplo: Valor Absoluto**
```cpp
#include <iostream>
#include <cstdlib> // Para abs()
using namespace std;

int main() {
    int num = -7;
    cout << "Valor absoluto de " << num << ": " << abs(num) << endl; // 7
    
    return 0;
}
```

---

## **5. Fracciones**
Las fracciones representan partes de un entero.

### **Ejemplo: Suma de Fracciones**
```cpp
#include <iostream>
using namespace std;

int mcd(int a, int b) {
    return b == 0 ? a : mcd(b, a % b);
}

void simplificar(int &num, int &den) {
    int divisor = mcd(num, den);
    num /= divisor;
    den /= divisor;
}

int main() {
    int num1 = 1, den1 = 2; // 1/2
    int num2 = 1, den2 = 4; // 1/4
    
    int numRes = num1 * den2 + num2 * den1;
    int denRes = den1 * den2;
    
    simplificar(numRes, denRes);
    
    cout << "Suma: " << numRes << "/" << denRes << endl; // 3/4
    
    return 0;
}
```

---

## **6. Números Decimales**
Los números decimales se representan con punto flotante (`float`, `double`).

### **Ejemplo: Conversión de Decimal a Fracción**
```cpp
#include <iostream>
#include <cmath>
using namespace std;

void decimalAFraccion(double decimal) {
    const double precision = 1.0E-6;
    int signo = decimal < 0 ? -1 : 1;
    decimal = abs(decimal);
    
    double entero = floor(decimal);
    decimal -= entero;
    
    int numerador = 1, denominador = 1;
    double error = decimal;
    
    for (int i = 2; i <= 1000; i++) {
        for (int j = 1; j < i; j++) {
            double currentError = abs((double)j / i - decimal);
            if (currentError < error) {
                error = currentError;
                numerador = j;
                denominador = i;
            }
        }
    }
    
    numerador += entero * denominador;
    numerador *= signo;
    
    cout << "Fracción: " << numerador << "/" << denominador << endl;
}

int main() {
    decimalAFraccion(0.75); // 3/4
    return 0;
}
```

---

## **7. Porcentajes**
Un porcentaje representa una fracción de 100.

### **Ejemplo: Cálculo de Porcentaje**
```cpp
#include <iostream>
using namespace std;

int main() {
    double valor = 200;
    double porcentaje = 15; // 15%
    
    double resultado = valor * (porcentaje / 100.0);
    
    cout << "El " << porcentaje << "% de " << valor << " es: " << resultado << endl; // 30
    
    return 0;
}
```

---

## **8. Razones y Proporciones**
Una razón compara dos cantidades, y una proporción iguala dos razones.

### **Ejemplo: Resolución de Proporciones**
```cpp
#include <iostream>
using namespace std;

int main() {
    // Si a/b = c/d, entonces d = (
