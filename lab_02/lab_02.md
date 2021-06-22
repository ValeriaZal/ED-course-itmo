Task:

Изменить в коде хотя бы два (можно больше) момента, которые теоретически, должны улучшить результат. Можно выбирать из этого:
1. Частота дискретизации (вместе с этим можно попробовать увеличить количество мелов, но будет считаться за одно). Учтите, что при изменении частоты, изменится и размеры спектрограмм. Чтобы взять 2 секунды звука, нужно будет уже брать не 64 отсчета в спектрограмме.
2. Изменить количество секунд, на котором обучаемся.
3. Добавить выбор случайного кусочка звука в EventDetectionDataset в функции getitem() (это должно сделать результат гораздо лучше)
4. Изменить optimizer на Adam
5. Изменить train/val разбиение
6. Добавить новый полносвязный и/или сверточный слой в класс модели

рекомендую еще увеличить количество эпох, так как моя модель, скорее всего, не доучилась


Solution:

Selected improvements: 4 and 6

Initial result:

Last epoch:

```
epoch # 49
mean train loss: 0.39413574237876864
train accuracy: 0.8741092636579573
mean val loss: 2.5871665492653846
val accuracy: 0.505
```

![base_loss](/lab_02/img/base_loss.png?raw=true)

![base_acc](/lab_02/img/base_acc.png?raw=true)

After improvement 4:

Last epoch:

```
epoch # 49
mean train loss: 0.059532693396113924
train accuracy: 0.9831902064681162
mean val loss: 4.897069442272186
val accuracy: 0.53875
```

![first_loss](/lab_02/img/first_loss.png?raw=true)

![first_acc](/lab_02/img/first_acc.png?raw=true)

After improvement 4 + 6:

Last epoch:

```
epoch # 49
mean train loss: 0.13043480157268358
train accuracy: 0.9585236616115476
mean val loss: 4.511532610654831
val accuracy: 0.55
```

![last_loss](/lab_02/img/last_loss.png?raw=true)

![last_acc](/lab_02/img/last_acc.png?raw=true)