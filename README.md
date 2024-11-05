# Es_GeoModel
Сейчас в мире достаточно популярно направление декарбонизации. Одним из видов проекта CCS является захоронение СО2 в водоносные горизонты. Для качественной технической оценки необходимо учитывать
коэффициент эффективности захоронения Es, который показывает, какой % от объема ловушки составляет закачанный СО2 на конец проекта. Для этого строят геологические и гидродинамические модели.  
________

**Описание данных:** В датасете представлены параметры, которые используются для построения геологической модели (минимальный и максимальный горизонтальные ранги, вертикальный ранг, сид, 
пористость, песчанистость, проницаемость и т.д.). Набор данных параметров характеризует обстановку осадконакопления, распределение коллектора и его объем и т.д. Такой набор параметров представлен для 540 моделей
с результатами расчетов Es.
________

**Задача:** Создать модель машинного обучения, которая предскажет коэффициент эффективности захоронения Es по параметрам геологической модели. 
________

**Цель:** С помощью построенной модели машинного обучения можно предварительно прогнозировать Es и проводить скрининг, используя параметры геологической модели и не строя гидродинамическую модель. 
________

**Используемые инструменты:**
* функции библиотеки Pandas;
* графики, гистограммы и тепловые карты, доступные в библиотеке matplotlib и seaborn;
* функции и модели библиотеки sklearn для работы с данными и регрессией (train_test_split, DecisionTreeRegressor, RandomForestRegressor, LinearRegression, DummyRegressor);
* бустинговые модели lgbm и catboost;
* подбор оптимальных гиперпараметров моделей с помощью RandomizedSearchCV;
* проверка модели на адеквантость с помощью константной модели DummyRegressor;
* построение диаграммы важности признаков.
________

**Полученные выводы:**
* MAPE тестовой выборки составил 0.097, что значительно ниже, чем у константной модели (0.464);
* 0.8 - такая доля предсказанных значений, у которых относительная разница с фактическими составляет <15%;
* 0.9 - такая доля предсказанных значений, у которых абсолютная разница с фактическими составляет <0.02.
