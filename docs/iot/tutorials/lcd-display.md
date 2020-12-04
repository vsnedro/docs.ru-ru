---
title: Отображение текста на ЖК-дисплее
description: Узнайте, как отображать символы на жидкокристаллических дисплеях с помощью библиотек Интернета вещей .NET.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: d4c3e373207e23877903491871f4d09e11000c1a
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "96594134"
---
<!--markdownlint-disable DOCSMD011 -->
# <a name="display-text-on-an-lcd"></a>Отображение текста на ЖК-дисплее

Отображение символов LCD удобно для отображения информации без внешнего монитора. Общедоступные дисплеи LCD могут быть подключены непосредственно к контактам GPIO, но такой подход требует использования до 10 ПИН-кодов GPIO. В сценариях, требующих подключения к комбинации устройств, часто бывает непрактичным, что большая часть заголовка GPIO к отображению символов нецелесообразна.

Многие производители продают 20x4 ЖК-экран с интегрированным расширительом GPIO. Отображение символов напрямую подключается к расширительу GPIO, который подключается к устройству Raspberry Pi через последовательный протокол Inter-Integrated канала (I2C).

В этом разделе вы будете использовать .NET для показа текста на ЖК-дисплее с помощью расширителя I2C GPIO.

## <a name="prerequisites"></a>Предварительные требования

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- [Отображение символов ЖК-дисплея 20x4 с помощью интерфейса I2C](https://www.bing.com/images/search?q=20x4+lcd+display+with+i2c)<span class="docon docon-navigate-external x-hidden-focus"></span>
- оптоволоконные кабеля с разъемами на обоих концах;
- Монтажная плата (необязательно/рекомендуется)
- Raspberry Pi GPIO (необязательно/рекомендуется)
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

> [!NOTE]
> Отображается множество производителей символов ЖК. Большинство структур идентичны, и изготовитель не должен делать никаких отличий от функциональности. Для справки Этот учебник был разработан с [LCD2004](https://www.sunfounder.com/lcd2004-module.html) <span class="docon docon-navigate-external x-hidden-focus"></span> .

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="prepare-the-hardware"></a>Подготовка оборудования

Используйте перемычки перемычек, чтобы подключить четыре контакта в расширитель I2C к устройству Raspberry Pi следующим образом:

- От ЗАЗЕМЛЕНия к заземлению
- От VCC до 5
- От SDA к SDA (GPIO 2)
- SCL для SCL (GPIO 3)

При необходимости ознакомьтесь со следующими рисунками:

| Интерфейс I2C (задняя часть экрана) | Raspberry Pi GPIO |
|---------------------------------|-------------------|
| :::image type="content" source="../media/character-display-i2c-thumb.png" alt-text="Изображение обратной стороны отображения символов, показывающее расширитель I2C GPIO." lightbox="../media/character-display-i2c.png"::: | :::image type="content" source="../media/gpio-pinout-diagram-thumb.png" alt-text="Схема, показывающая схему контактов заголовка Raspberry Pi GPIO. Образ с Raspberry Pi Foundation." lightbox="../media/gpio-pinout-diagram.png":::<br />[Образ с Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/) <span class="docon docon-navigate-external x-hidden-focus"></span> .
 |

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a>Создание приложения

Выполните следующие действия в предпочитаемой среде разработки:

1. Создайте новое консольное приложение .NET с помощью [интерфейса командной строки .NET](../../core/tools/dotnet-new.md) или [Visual Studio](../../core/tutorials/with-visual-studio.md). Назовите его *лкдтуториал*.

    ```dotnetcli
    dotnet new console -o LcdTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. Замените содержимое *Program.cs* кодом из этого примера.

    :::code language="csharp" source="~/iot-samples/tutorials/LcdTutorial/Program.cs" :::

    В предыдущем коде:

    - [Объявление using](../../csharp/whats-new/csharp-8.md#using-declarations) создает экземпляр `I2cDevice` , вызывая метод `I2cDevice.Create` и передавая новый `I2cConnectionSettings` с `busId` `deviceAddress` параметрами и. Это `I2cDevice` представляет ШИНУ I2C. `using`Объявление гарантирует, что объект удален и аппаратные ресурсы освобождаются должным образом.

        > [!WARNING]
        > Адрес устройства для расширителя GPIO зависит от микросхемы, используемой производителем. Расширители GPIO, оснащенные PCF8574, используют адрес `0x27` , а те, кто использует микросхемы PCF8574A `0x3F` . Обратитесь к документации ЖК-дисплея.

    - Другое `using` объявление создает экземпляр `Pcf8574` и передает его в `I2cDevice` конструктор. Этот экземпляр представляет расширитель GPIO.
    - Другое `using` объявление создает экземпляр `Lcd2004` для представления отображения. В конструктор передается несколько параметров, описывающих параметры, используемые для взаимодействия с расширительом GPIO. Расширитель GPIO передается в качестве `controller` параметра.
    - `while`Цикл выполняется бессрочно. Каждая итерация:
        1. Очищает экран.
        1. Устанавливает позицию курсора в первую позицию в текущей строке.
        1. Записывает текущее время на экран в текущей позиции курсора.
        1. Выполняет итерацию счетчика текущей строки.
        1. Спящий режим 1000 мс.

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. Запустите приложение на устройстве Raspberry Pi, перейдя в каталог развертывания и запустив исполняемый файл.

    ```bash
    ./LcdTutorial
    ```

    Обратите внимание на отображение символа ЖК-дисплея, так как текущее время отображается в каждой строке.

    > [!TIP]
    > Если дисплей горит, но текст не отображается, попробуйте настроить контрастность на обратной стороне экрана.

1. Завершите программу, нажав клавиши <kbd>CTRL + C</kbd>.

Поздравляем! Вы выделили текст на ЖК-мониторе, используя I2C и расширитель GPIO!

## <a name="get-the-source-code"></a>Получение исходного кода

Источник этого руководства [доступен на сайте GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/LcdTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span> .

## <a name="next-steps"></a>Дальнейшие действия

> [!div class="nextstepaction"]
> [Научитесь использовать общего назначения ввода-вывода для мигания индикатора](../tutorials/blink-led.md)
