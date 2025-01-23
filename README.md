# Homework


## Інсталяція залежностей

```bash
pip install -r requirements.txt
```


## Завдання

1. Допишіть в файлі `kfold.py` функції `kfold_cross_validation` та `evaluate_accuracy` для того щоб порахувати точність роботи KNN алгоритму.

2. Порахуйте для різних `k` в `KNN` точність на **тестовому** датасеті і запишіть в `README.md`, `k` беріть з таблички нижче

 k | Accuracy
---|----------
 3 | ???
 4 | ???
 5 | ???
 6 | ???
 7 | ???
 9 | ???
10 | ???
15 | ???
20 | ???
21 | ???
40 | ???
41 | ???

Які можна зробити висновки про вибір `k`?

3. Знайшовши найкращий `k` змініть `num_folds` (в `main()`) та подивіться чи в середньому точність на валідаційних датасетах схожа з точністю на тестовому датасеті.

## Відповідь



 num_folds = 5 |  KNN with k = 1
---------------------------|--------------------
Predicted 200/200 samples  | Accuracy: 0.87  
Predicted 200/200 samples   | Accuracy: 0.9   
Predicted 200/200 samples   | Accuracy: 0.84  
Predicted 200/200 samples   | Accuracy: 0.85  
Predicted 200/200 samples   | Accuracy: 0.86  


k | Accuracy
---|---------
3 | 0.820
4 | 0.833
5 | 0.828
6 | 0.830
7 | 0.807
9 | 0.802
10 | 0.810
15 | 0.792
20 | 0.777
21 | 0.777
40 | 0.733
41 | 0.733

Максимальна точність виходить при k=4 (0.833) або k=6 (0.830).
При меньшому k модель ще є underfitting, але при більшому вже є overfitting, бо точність вже знижується.

num_folds = 10 |  KNN with k = 4
--------------|------------------
Predicted 100/100 samples | Accuracy: 0.85
Predicted 100/100 samples | Accuracy: 0.86
Predicted 100/100 samples | Accuracy: 0.92
Predicted 100/100 samples | Accuracy: 0.87
Predicted 100/100 samples | Accuracy: 0.87
Predicted 100/100 samples | Accuracy: 0.84
Predicted 100/100 samples | Accuracy: 0.86
Predicted 100/100 samples | Accuracy: 0.88
Predicted 100/100 samples | Accuracy: 0.82
Predicted 100/100 samples | Accuracy: 0.9

Тобто ми бачимо,що з найкращим значенням k =4 при зміні кількості фолдів (num_folds = 10) зрезультати крос-валідації (точність на різних фолдах) залишаються в тому ж діапазоні (від ~0.82 до ~0.92), що свідчить про стабільність моделі.

