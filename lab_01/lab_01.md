Task:

1. Есть Гитхаб куда будут залиты исходники лабы
2. Есть гуглдиск и гуглколаб - реализоавно приложение hello world
3. Загружена база на гугл диск
4. Расчитаны фичи с помощью либроза и сохранены в pkl на гуглдиск
5. Данные разделены на трэйн и валидацию!!
6. реализован ML классификатор
7. Посчитана метрика f1 и конф матрица на трэйне и на врефикации
8. Обновлены f1 по результатам перебора параметров

Solution:

1. GitHub: https://github.com/ValeriaZal/ED-course-itmo
2. Used ipynb in VS Code
3. Used local copy of dataset from Kaggle: https://www.kaggle.com/chrisfilo/urbansound8k
4. Used `librosa.feature.mfcc(y=signal, sr=sr)` (see "Extract features (MFCC)" in lab_01.ipynb)
5. See "Divide into train/eval" in lab_01.ipynb (comment: data is already balanced by creators in 10 folders, so additional shuffling is not recommended for this data)
6. See "Base classificator" in lab_01.ipynb (svm.SVC() with default parameters)
7. Result:

7.1. F1-score

7.1.1. Train data

```
              precision    recall  f1-score   support

           0       0.48      0.60      0.53       600
           1       0.79      0.50      0.61       306
           2       0.52      0.62      0.56       600
           3       0.79      0.64      0.71       600
           4       0.73      0.63      0.68       600
           5       0.78      0.33      0.46       624
           6       0.74      0.83      0.78       230
           7       0.48      0.82      0.61       668
           8       0.83      0.71      0.77       607
           9       0.49      0.49      0.49       600

    accuracy                           0.61      5435
   macro avg       0.66      0.62      0.62      5435
weighted avg       0.65      0.61      0.61      5435
```

7.1.2. Test data

```
              precision    recall  f1-score   support

           0       0.20      0.23      0.21       300
           1       0.54      0.34      0.42        90
           2       0.46      0.61      0.52       300
           3       0.73      0.58      0.64       300
           4       0.54      0.49      0.51       300
           5       0.46      0.20      0.28       283
           6       0.79      0.74      0.76       112
           7       0.33      0.62      0.43       236
           8       0.67      0.65      0.66       239
           9       0.52      0.42      0.47       300

    accuracy                           0.48      2460
   macro avg       0.52      0.49      0.49      2460
weighted avg       0.50      0.48      0.48      2460
```

7.2. Confusion matrix

7.2.1. Train data

Absolute values

![base_clf_cm_abs_train](/lab_01/img/base_clf_cm_abs_train.png?raw=true)

Normalized by true labels' number

![base_clf_cm_norm_train](/lab_01/img/base_clf_cm_norm_train.png?raw=true)

7.2.2. Test data

Absolute values

![base_clf_cm_abs_test](/lab_01/img/base_clf_cm_abs_test.png?raw=true)

Normalized by true labels' number

![base_clf_cm_norm_test](/lab_01/img/base_clf_cm_norm_test.png?raw=true)

8. Result:

8.1. F1-score

8.1.1. Train data

```
              precision    recall  f1-score   support

           0       0.74      0.84      0.79       600
           1       0.92      0.87      0.90       306
           2       0.78      0.79      0.78       600
           3       0.95      0.84      0.89       600
           4       0.92      0.87      0.89       600
           5       0.88      0.84      0.86       624
           6       0.95      0.97      0.96       230
           7       0.80      0.94      0.87       668
           8       0.95      0.93      0.94       607
           9       0.80      0.72      0.76       600

    accuracy                           0.85      5435
   macro avg       0.87      0.86      0.86      5435
weighted avg       0.86      0.85      0.85      5435
```

8.1.2. Test data

```
              precision    recall  f1-score   support

           0       0.31      0.18      0.23       300
           1       0.64      0.67      0.65        90
           2       0.50      0.61      0.55       300
           3       0.83      0.63      0.72       300
           4       0.52      0.52      0.52       300
           5       0.46      0.39      0.42       283
           6       0.89      0.82      0.86       112
           7       0.44      0.70      0.54       236
           8       0.63      0.74      0.68       239
           9       0.49      0.48      0.49       300

    accuracy                           0.54      2460
   macro avg       0.57      0.57      0.56      2460
weighted avg       0.54      0.54      0.53      2460
```

8.2. Confusion matrix

8.2.1. Train data

Absolute values

![best_clf_cm_abs_train](/lab_01/img/best_clf_cm_abs_train.png?raw=true)

Normalized by true labels' number

![best_clf_cm_norm_train](/lab_01/img/best_clf_cm_norm_train.png?raw=true)

8.2.2. Test data

Absolute values

![best_clf_cm_abs_test](/lab_01/img/best_clf_cm_abs_test.png?raw=true)

Normalized by true labels' number

![best_clf_cm_norm_test](/lab_01/img/best_clf_cm_norm_test.png?raw=true)