# PZ-11
<img width="944" height="352" alt="2026-04-10_14-03-03" src="https://github.com/user-attachments/assets/db4ddb3e-67ca-4385-9ba3-023e116ec843" />

Задание 1

~~~

#include <iostream>

using namespace std;

int main() {
    setlocale(LC_ALL, "Russian");

    int n;
    cin >> n;

    // Ваш код:
    for (int i = 1; i <= n; ++i) {
        cout << i;
        if (i < n) {
            cout << " ";
        }
    }
    cout << endl;

    return 0;
}

~~~

Задание 2

~~~
#include <iostream>

using namespace std;

int main() {
    setlocale(LC_ALL, "Russian");

    int n;
    cin >> n;

    // Ваш код:
    int sum = 0;
    for (int i = 1; i <= n; ++i) {
        sum += i;
    }
    cout << sum << endl;

    return 0;
}

~~~

Задание 3

~~~
#include <iostream>

using namespace std;

int main() {
    setlocale(LC_ALL, "Russian");

    // Ваш код:
    int number;
    int sum = 0;

    while (cin >> number) {
        if (number == 0) {
            break;
        }
        sum += number;
    }

    cout << sum << endl;

    return 0;
}

~~~

Задание 4

~~~
#include <iostream>

using namespace std;

int main() {
    setlocale(LC_ALL, "Russian");
    int n;
    cin >> n;

    // Ваш код:
    bool isFirst = true; // флаг для контроля пробелов между числами

    for (int i = 1; i <= n; ++i) {
        if (i % 2 == 0) { // проверяем, чётное ли число
            if (!isFirst) {
                cout << " "; // добавляем пробел перед числом, если это не первое чётное число
            }
            cout << i;
            isFirst = false;
        }
    }
    cout << endl;

    return 0;
}

~~~

Задание 5

~~~
#include <iostream>

using namespace std;

int main() {
    setlocale(LC_ALL, "Russian");

    int n;
    cin >> n;

    // Ваш код:
    long long factorial = 1; // используем long long для поддержки больших значений

    // Обрабатываем случай N = 0: 0! = 1 по определению
    if (n < 0) {
        // Для отрицательных чисел факториал не определён
        cout << "Ошибка: факториал отрицательного числа не определён" << endl;
        return 0;
    }

    for (int i = 1; i <= n; ++i) {
        factorial *= i;
    }

    cout << factorial << endl;

    return 0;
}

~~~

Задание 6

~~~
#include <iostream>

using namespace std;

int main() {
    setlocale(LC_ALL, "Russian");

    int n;
    cin >> n;

    // Ваш код:
    int count = 0;

    if (n == 0) {
        count = 0; // согласно условию, 0 игнорируем — значит, количество цифр 0
    } else {
        n = abs(n); // учитываем отрицательные числа: берём модуль
        while (n > 0) {
            n /= 10;  // убираем последнюю цифру числа
            ++count;  // увеличиваем счётчик цифр
        }
    }

    cout << count << endl;

    return 0;
}

~~~

Задание 7

~~~
#include <iostream>
#include <cmath>

using namespace std;

int main() {
    setlocale(LC_ALL, "Russian");

    int n;
    cin >> n;

    // Ваш код:
    bool isPrime = true;

    // Особые случаи
    if (n <= 1) {
        isPrime = false;
    } else if (n == 2) {
        isPrime = true;
    } else if (n % 2 == 0) {
        isPrime = false; // чётные числа > 2 не являются простыми
    } else {
        // Проверяем нечётные делители от 3 до sqrt(n)
        int limit = static_cast<int>(sqrt(n));
        for (int i = 3; i <= limit; i += 2) {
            if (n % i == 0) {
                isPrime = false;
                break; // нашли делитель — дальше проверять не нужно
            }
        }
    }

    if (isPrime) {
        cout << "Простое" << endl;
    } else {
        cout << "Не простое" << endl;
    }

    return 0;
}

~~~

Задание 8

~~~
#include <iostream>

using namespace std;

int main() {
    setlocale(LC_ALL, "Russian");

    int n;
    cin >> n;

    // Ваш код:
    int i = 1; // внешний счётчик строк (множитель 1)
    while (i <= n) {
        int j = 1; // внутренний счётчик столбцов (множитель 2)
        while (j <= n) {
            cout << i * j; // выводим произведение текущих множителей
            if (j < n) {
                cout << " "; // пробел между числами в строке, кроме последнего
            }
            ++j; // увеличиваем внутренний счётчик
        }
        cout << " " << endl; // добавляем пробел перед переводом строки, как в образце
        ++i; // увеличиваем внешний счётчик
    }

    return 0;
}

~~~
