---
title: Сигнал светодиодного индикатора
description: Сведения о том, как мигающий светодиодный индикатор с помощью библиотек Интернета вещей .NET.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: 07a050c0655f9cae3d7f2b924c0dd07ac1c6c0b9
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "96594149"
---
# <a name="blink-an-led"></a>Сигнал светодиодного индикатора

ПИН-коды универсального ввода-вывода (GPIO) можно контролировать отдельно. Это полезно для управления индикаторами, ретрансляторами и другими устройствами с отслеживанием состояния. В этом разделе вы будете использовать .NET и контакты GPIO Raspberry Pi для питания СВЕТОИНДИКАТОРА и мигающие его повторно.

## <a name="prerequisites"></a>Предварительные требования

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- ИНДИКАТОР на 5 мм
- резистор ω 330
- монтажная плата;
- оптоволоконные кабеля с разъемами на обоих концах;
- Raspberry Pi GPIO (необязательно/рекомендуется)
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

[!INCLUDE [ensure-ssh](../includes/ensure-ssh.md)]

## <a name="prepare-the-hardware"></a>Подготовка оборудования

Используйте аппаратные компоненты для создания канала, как показано на следующей схеме:

:::image type="content" source="../media/rpi-led_bb-thumb.png" alt-text="Схема Фритзинг, показывающая канал с ИНДИКАТОРом и резистором" lightbox="../media/rpi-led_bb.png":::

На приведенном выше рисунке изображены следующие подключения:

- GPIO 18 — анод LED (более длинный, положительный)
- Катод индикатора (короткий, отрицательный) до 330 Ωного резистора (End)
- 330 ω резистор (другой конец) к заземлению

[!INCLUDE [tutorial-rpi-gpio](../includes/tutorial-rpi-gpio.md)]

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a>Создание приложения

Выполните следующие действия в предпочитаемой среде разработки:

1. Создайте новое консольное приложение .NET с помощью [интерфейса командной строки .NET](../../core/tools/dotnet-new.md) или [Visual Studio](../../core/tutorials/with-visual-studio.md). Назовите его *блинктуториал*.

    ```dotnetcli
    dotnet new console -o BlinkTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. Замените содержимое *Program.cs* кодом из этого примера.

    :::code language="csharp" source="~/iot-samples/tutorials/BlinkTutorial/Program.cs" :::

    В предыдущем коде:

    - [Объявление using](../../csharp/whats-new/csharp-8.md#using-declarations) создает экземпляр `GpioController` . `using`Объявление гарантирует, что объект удален и аппаратные ресурсы освобождаются должным образом.
    - Для выходных данных открыт ПИН-код GPIO 18
    - `while`Цикл выполняется бессрочно. Каждая итерация:
        1. Записывает значение в GPIO-контактный 18. Если `ledOn` имеет значение true, то записывает `PinValue.High` (on). В противном случае он выполняет запись `PinValue.Low` .
        1. Спящий режим 1000 мс.
        1. Переключает значение `ledOn` .

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. Запустите приложение на устройстве Raspberry Pi, перейдя в каталог развертывания и запустив исполняемый файл.

    ```bash
    ./BlinkTutorial
    ```

    ИНДИКАТОР мигает и включается каждую секунду.

1. Завершите программу, нажав клавиши <kbd>CTRL + C</kbd>.

Поздравляем! Вы использовали GPIO для мигания индикатора.

## <a name="get-the-source-code"></a>Получение исходного кода

Источник этого руководства [доступен на сайте GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/BlinkTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span> .

## <a name="next-steps"></a>Дальнейшие действия

> [!div class="nextstepaction"]
> [Узнайте, как считывать условия окружающей среды из датчика.](../tutorials/temp-sensor.md)
