## **1. Классы эквивалентности**

### **Сумма кредита (в рублях)**
| Тип значения            | Диапазон или значение                  |
|------------------------|----------------------------------------|
| Корректные             | 1 000 – 1 000 000 000 000              |
| Меньше допустимого     | < 1 000                                |
| Больше допустимого     | > 1 000 000 000 000                    |
| Неверный формат        | Буквы, специальные символы, пустые поля |

### **Срок кредита (в месяцах)**
| Тип значения            | Диапазон или значение           |
|------------------------|----------------------------------|
| Корректные             | 1 – 720 (1 месяц – 60 лет)       |
| Меньше допустимого     | < 1                              |
| Больше допустимого     | > 720                            |
| Неверный формат        | Текст, дробные числа             |

### **Процентная ставка (в год)**
| Тип значения            | Диапазон или значение      |
|------------------------|-----------------------------|
| Корректные             | от -20 до 400               |
| Меньше допустимого     | < -20                       |
| Больше допустимого     | > 400                       |
| Неверный формат        | Буквы, символы              |

### **Тип платежа**
| Тип значения            | Примеры                          |
|------------------------|----------------------------------|
| Корректные             | Аннуитетный, Дифференцированный |
| Неверные               | Не выбран, произвольный текст   |

---

## **2. Граничные значения**

### **Сумма кредита**
| Категория         | Значение             |
|-------------------|----------------------|
| Ниже нижней       | 999                  |
| Нижняя граница    | 1 000                |
| Верхняя граница   | 1 000 000 000 000    |
| Выше верхней      | 1 000 000 000 001    |

### **Срок кредита**
| Категория         | Значение    |
|-------------------|-------------|
| Ниже нижней       | 0           |
| Нижняя граница    | 1           |
| Верхняя граница   | 720         |
| Выше верхней      | 721         |

### **Процентная ставка**
| Категория         | Значение    |
|-------------------|-------------|
| Ниже нижней       | -21         |
| Нижняя граница    | -20         |
| Верхняя граница   | 400         |
| Выше верхней      | 401         |

---

## **3. Таблица тестовых данных**

| №  | Сумма (₽)             | Срок (мес) | Ставка (%) | Тип платежа        | Ожидаемый результат                                   |
|----|------------------------|------------|------------|---------------------|--------------------------------------------------------|
| 1  | 1 000                  | 1          | -20        | Аннуитетный         | Допустимые минимальные значения                       |
| 2  | 1 000 000 000 000      | 720        | 400        | Дифференцированный  | Допустимые максимальные значения                      |
| 3  | 999                    | 12         | 10.0       | Аннуитетный         | Ошибка: сумма ниже минимального порога               |
| 4  | 500 000                | 0          | 15.0       | Дифференцированный  | Ошибка: срок ниже допустимого                        |
| 5  | 10 000                 | 24         | -25.0      | Аннуитетный         | Ошибка: процентная ставка ниже -20%                 |
| 6  | 100 000                | 36         | 401        | Дифференцированный  | Ошибка: ставка превышает 400%                       |
| 7  | 200 000                | 48         | 15.5       | (не выбран)         | Ошибка: тип платежа не выбран                       |
| 8  | abc                    | 12         | 10         | Аннуитетный         | Ошибка: сумма введена некорректно                   |
| 9  | 150 000                | десять     | 12.5       | Дифференцированный  | Ошибка: срок не распознан как число                 |
| 10 | 1 000 000              | 60         | тридцать   | Аннуитетный         | Ошибка: процент задан в неверном формате            |
