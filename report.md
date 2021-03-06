# Отчёт о тестировании приложения "Money Transfer"

## Краткое описание

Приложение суммирует приход средств на счет где: 

* balance - состояние счета.
* transfer - входящий перевод.
* total - итоговая сумма.

Работает исправно, при условии что total (итоговая сумма) < 2_146_999_999.
В диапазоне значений total > 2_146_999_999 возникает ошибка в виде отрицительной суммы счета.

## Описание тестов

Проведено функциональное тестирование с использованием позитивных и негативных сценариев. 

### Тестовые данные позитивных сценариев (ожидаемый и фактический результат совпадают)

* balance = 2_000_000_000; transfer = 146_999_999;
* balance = 2_000_000_000; transfer = 130_000_000
* balance = 2_000_000_000; transfer = 13

### Тестовые данные негативных сценариев (ожидаемый и фактический результат не совпадают)

* balance = 2_000_000_000; transfer = 200_999_999
* balance = 2_000_000_000; transfer = 500_000_000
* balance = 2_000_000_000; transfer = 150_000_000

## Результаты

 [баг-репорт](https://github.com/shubartsova/money-transfer/issues/1)

## Общие рекомендации

Увеличить область допустимых значений.