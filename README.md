# Wells_NTG
Предсказание песчанистости в точках между скважинами

Песчанистость - отношение толщины слоя песка ко всей глубине скважины, поэтому очевидно. что задачу можно свести к задаче восстановления рельефа по заданным точкам.

Задача осложняется малой обучающей выборкой (10% от того, что надо предсказать) и малым количеством признаков (только координаты местоположения скважины в пространстве).

Базовый подход - RBF интерполяция. Лучший результат на валидационной выборке - аппроксимирующая функция "multiquadric".

Далее были сгенерированы дополнительные признаки и расстояния до ближайших точек и песчанистость в них, и использованы модели классического машинного обучения.

Так как данных мало - результат оценивался по кросс-валидации и визуально.

В качестве финальной модели использовался Stacking Regressor с xgboost, bayesian ridge, KNN, финальная модель - linear regression с регуляризацией ridge.
