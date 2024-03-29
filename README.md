# Bank
Задачей данного проекта является предложить наилучшую модель, которая спрогнозирует, какие клиенты вскоре могут уйти от банка, чтобы маркетологи сосредоточились на их удержании. 
В данном проекте была обучена модель, которая прогнозирует уход клиентов от банка. Для обучения использовались уже имеющиеся данные о пользователях, перешедших на новые тарифные планы.
В ходе проекта были выполнены следующие действия:

1.	Данные изучены и подготовлены для обучения моделей:
•	наименования столбцов были придевены к удобному формату.
•	обнаруженные пропуски в данных о количестве лет сотрудничества с банком (9% или 900 записей) были заполнены средним значением.
•	составлен рабочий сет из значимых признаков для дальнейшего обучения модели.
•	применено прямое кодирование категориальных признаков Страна проживания и Пол.
•	были обнаружены взаимосвязи между оттоком клиентов и возрастом - в основном ушли клиенты в возрасте от 40 до 60 лет, а также количеством используемых банковских продуктов - клиенты, польующиеся 3мя продуктами и выше, переключились на другие банки.
•	рабочий датасет был разделен на обучающую, валидационную и тестовую выборки.
•	применено масштабирование количественных признаков.

2.	Исследован баланс классов. На ушедших клиентов приходится всего 2037 (около 20%) от всех записей, классы в целевом признаке сильно несбалансированы.
  
3.	На данных без учета дисбаланса классов подобрана наилучшая модель Случайного леса с оптимальной глубиной 15 и количеством деревьев 37. Значение F1 меры 0.58, AUC-ROC - 0.85.
4.	Наиболее действенным методом ухода от дисбаланса оказался метод Взвешивания классов, а наилучшая модель с наиболее высокими метриками качества - модель Случайного леса с максимальной глубиной 11 и количеством деревьев 32. При применении данной техники значение F1 меры у модели составило 0.601, а метрики auc-roc - 0.846.
5.	На финальной проверке модели использовалась тестовая выборка, ранее не участвовшая в обучении и валидации. Значение F1 меры на тестовых данных оказалось выше, чем в предыдущих итерациях - 0.625. Это значит, что модель научилась достаточно хорошо распознавать клиентов, собирающихся сменить банк. Значение AUC-ROC повысилось до 0.854: модель отрабатывает лучше среднего.

