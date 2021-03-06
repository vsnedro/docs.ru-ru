---
title: Считывание с датчика условий окружающей среды
description: Узнайте, как читать термпературе, barometric pressureную нагрузку и влажности с помощью библиотек .NET IoT.
author: camsoper
ms.author: casoper
ms.date: 11/14/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: bc5c2b9f0876603c152da859547c58b83826969c
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259841"
---
# <a name="read-environmental-conditions-from-a-sensor"></a>Считывание с датчика условий окружающей среды

Одним из наиболее распространенных сценариев для устройств IoT является обнаружение условий окружающей среды. Для мониторинга температуры, влажности, barometric pressure давления и многого другого доступны различные датчики.

В этом разделе вы будете использовать .NET для считывания условий окружающей среды из датчика.

## <a name="prerequisites"></a>Предварительные требования

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- [BME280](https://learn.adafruit.com/adafruit-bme280-humidity-barometric-pressure-temperature-sensor-breakout) влажности/barometric pressure/нагрузка датчика температуры
- оптоволоконные кабеля с разъемами на обоих концах;
- Монтажная плата (необязательно)
- Плата за Raspberry Pi GPIO (необязательно)
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

> [!IMPORTANT]
> Существует множество производителей BME280ов. Большинство структур похожи, и изготовитель не должен делать никаких отличий от функциональности. В этом руководстве будет предпринята попытка учитывать вариации. Убедитесь, что ваша BME280ная схема включает интерфейс канала Inter-Integrated (I2C).

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="prepare-the-hardware"></a>Подготовка оборудования

Используйте аппаратные компоненты для создания канала, как показано на следующей схеме:

:::image type="content" source="../media/rpi-bmp280_i2c-thumb.png" alt-text="Схема Фритзинг, показывающая подключение от Raspberry Pi к BME280ной доске" lightbox="../media/rpi-bmp280_i2c.png":::

Ниже приведены подключения Raspberry Pi к BME280.

- от 3.3 v к VIN *или* 3v3 (отображается красным цветом)
- От заземления к ЗАЗЕМЛЕНию (черный)
- SDA (GPIO 2) к SDI *или* SDA (синий)
- SCL (GPIO 3) в SCK *или* SCL (оранжевый)

[!INCLUDE [tutorial-rpi-gpio](../includes/tutorial-rpi-gpio.md)]

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a>Создание приложения

Выполните следующие действия в предпочитаемой среде разработки:

1. Создайте новое консольное приложение .NET с помощью [интерфейса командной строки .NET](../../core/tools/dotnet-new.md) или [Visual Studio](../../core/tutorials/with-visual-studio.md). Назовите его *сенсортуториал*.

    ```dotnetcli
    dotnet new console -o SensorTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. Замените содержимое *Program.cs* кодом из этого примера.

    :::code language="csharp" source="~/iot-samples/tutorials/SensorTutorial/Program.cs" :::

    В приведенном выше коде:

    - `i2cSettings` параметру присваивается новый экземпляр `I2cConnectionSettings` . Конструктор задает `busId` для параметра значение 1, а `deviceAddress` параметр — значение `Bme280.DefaultI2cAddress` .

        > [!IMPORTANT]
        > Некоторые производители BME280 используют значение дополнительного адреса. Для этих устройств используйте `Bme280.SecondaryI2cAddress` .

    - [Объявление using](../../csharp/whats-new/csharp-8.md#using-declarations) создает экземпляр `I2cDevice` путем вызова `I2cDevice.Create` и передачи `i2cSettings` . Это `I2cDevice` представляет ШИНУ I2C. `using`Объявление гарантирует, что объект удален и аппаратные ресурсы освобождаются должным образом.
    - Другое `using` объявление создает экземпляр `Bme280` для представления датчика. `I2cDevice`Передается в конструктор.
    - Время, необходимое для использования микросхемы для получения измерений с текущими параметрами микросхемы (по умолчанию), извлекается путем вызова `GetMeasurementDuration` .
    - `while`Цикл выполняется бессрочно. Каждая итерация:
        1. Очищает консоль.
        1. Задает режим питания `Bmx280PowerMode.Forced` . Это заставляет микросхемы выполнять одно измерение, сохранять результаты, а затем переходить в спящий режим.
        1. Считывает значения температуры, давления, влажности и высоты.

            > [!NOTE]
            > Высота вычисляется привязкой устройства. Эта перегрузка метода `TryReadAltitude` использует значение "давление уровня моря" для создания оценки.

        1. Записывает текущие условия среды в консоль.
        1. Спящий режим 1000 мс.

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. Запустите приложение на устройстве Raspberry Pi, перейдя в каталог развертывания и запустив исполняемый файл.

    ```bash
    ./SensorTutorial
    ```

    Обратите внимание на вывод датчика в консоли.

1. Завершите программу, нажав клавиши <kbd>CTRL + C</kbd>.

Поздравляем! Вы использовали I2C для считывания значений с датчика давления температуры/влажности/barometric pressure!

## <a name="get-the-source-code"></a>Получение исходного кода

Источник этого руководства [доступен на сайте GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/SensorTutorial).

## <a name="next-steps"></a>Дальнейшие действия

> [!div class="nextstepaction"]
> [Узнайте, как отображать текст на ЖК-дисплее](../tutorials/lcd-display.md)
