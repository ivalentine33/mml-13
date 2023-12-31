# MML-13
<h2>Задача: проанализировать ВВП африканской страны Гана</h2>
<div>
Необходимо исследовать временной ряд и сделать выводы.<br />
Данные представлены в формате CSV. Файл содержит временную метку и размер ВВП за указанный год.<br />
Имеются данные ою уровне ВВП Ганы за период с 1960 по 2021 годы.<br />
Из анализа ряда можно сделать выводы о наличии тренда, отсутствии сезонности и остатков.<br />
При разделени выборки в качестве тестовой были взяты значения за последние три года.<br />
Тест Дики-Фуллера ппоказал отсутствие стационарности у исходного ряда. Для приведения ряда к стационарному пришлось трижды его дифферецировать.<br />
Так как ряд не относитсчя к стационарным, но при этом отсутствует сезонность, была применена модель ARIMA. Из графикоа автокорреляции и частичной автокорреляции были выбраны следующие параметры для модели:
<ul>
<li>p = 2</li>
<li>q = 1</li>
<li>d = 3</li>
</ul>
При этих параметрах значение AIC = 2659.231<br />
Автоматический поиск оптимальных параметров дал тот же самый результат.<br />
Проверка ряда на пропуски показала, что пропущенных дат нет, но за 1961 год имеется нулевое значение ВВП. Была проведена интерполяция и проведено повторное исследование ряда.<br />
Результат повторного моделирования с использованием ARIMA немного изменил предсказание и AIC.<br />
Следующим шагом стало исследование волатильности ряда.<br />
При исследовании волатильности пришлось подбирать параметры, отличные от тех, что получались исходя из графика частичной автокорреляции и кареллограммы. Кроме того, поиск оптимальных параметров также выдал результаты, не подходящие для модели (p = 0). После ручного подбора были выбраны следующие параметры для моделирования:
<ul>
<li>p = 7</li>
<li>q = 7</li>
<li>d = 0 (ряд стационарный)</li>
</ul>
Результат моделирования показал, что GARCH-модель и линейная регрессия не смогли уловить дисперсию, что можно объяснить малым количеством тестовых данных в выборке и отсутствием похожего поведения в обучающей выборке.
</div>





   
