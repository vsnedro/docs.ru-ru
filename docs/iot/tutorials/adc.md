---
title: Считывание значений с аналогово-цифрового преобразователя
description: Узнайте, как считывать значения переменного напряжения с помощью аналогового в цифровом преобразователе.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: 509616e3423fbb83b74bfbb8ecec1a7df49f0a20
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259748"
---
<!--markdownlint-disable DOCSMD011 -->
# <a name="read-values-from-an-analog-to-digital-converter"></a>Считывание значений с аналогово-цифрового преобразователя

Аналогово-цифровой преобразователь (ADC) — это устройство, которое может считывать значение аналогового входного напряжения и преобразовывать его в цифровое значение. ADCs используется для считывания значений из сермисторс, потентиометерс и других устройств, которые меняют сопротивления на основе определенных условий.

В этом разделе вы будете использовать .NET для чтения значений из ADC при модуляции входного напряжения с помощью потентиометер.

## <a name="prerequisites"></a>Предварительные требования

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- [MCP3008](https://www.microchip.com/wwwproducts/MCP3008) аналогово-цифровой преобразователь
- 3-контактный потентиометер
- монтажная плата;
- оптоволоконные кабеля с разъемами на обоих концах;
- Raspberry Pi GPIO (необязательно/рекомендуется)
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

[!INCLUDE [prepare-pi-spi](../includes/prepare-pi-spi.md)]

## <a name="prepare-the-hardware"></a>Подготовка оборудования

Используйте аппаратные компоненты для создания канала, как показано на следующей схеме:

:::image type="content" source="../media/rpi-trimpot_spi-thumb.png" alt-text="Схема Фритзинг, показывающая цепь с MCP3008 ADC и потентиометер" lightbox="../media/rpi-trimpot_spi.png":::

MCP3008 использует для взаимодействия интерфейс Serial периферийные устройства (SPI). Ниже приведены подключения из MCP3008 к Raspberry Pi и потентиометер:

- V<sub>дд</sub> в 3,3 в (отображается красным цветом)
- V<sub>ссылка</sub> на 3,3 в (красный)
- АГНД на землю (черный)
- КЛК СКЛК (оранжевый)
- Г<sub>в</sub> мисо (оранжевый)
- D<sub>в</sub> Моси (оранжевый)
- CS/SHDN CE0 (зеленый)
- ДГНД на землю (черный)
- CH0 в переменную (средний) ПИН-код на потентиометер (желтый)

Предоставьте напряжение 3,3 в и заземление на внешних контактах на потентиометер. Порядок не важен.

При необходимости ознакомьтесь со следующими схемами контактов:

| MCP3008  | Raspberry Pi GPIO |
|----------|-------------------|
| :::image type="content" source="../media/mcp3008-diagram-thumb.png" alt-text="Схема, показывающая схему контактов MCP3008" lightbox="../media/mcp3008-diagram.png"::: | :::image type="content" source="../media/gpio-pinout-diagram-thumb.png" alt-text="Схема, показывающая схему контактов заголовка Raspberry Pi GPIO. Образ с Raspberry Pi Foundation." lightbox="../media/gpio-pinout-diagram.png":::<br />[Образ с Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/).
 |

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a>Создание приложения

Выполните следующие действия в предпочитаемой среде разработки:

1. Создайте новое консольное приложение .NET с помощью [интерфейса командной строки .NET](../../core/tools/dotnet-new.md) или [Visual Studio](../../core/tutorials/with-visual-studio.md). Назовите его *адктуториал*.

    ```dotnetcli
    dotnet new console -o AdcTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. Замените содержимое *Program.cs* кодом из этого примера.

    :::code language="csharp" source="~/iot-samples/tutorials/AdcTutorial/Program.cs" :::

    В приведенном выше коде:

    - `hardwareSpiSettings` параметру присваивается новый экземпляр `SpiConnectionSettings` . Конструктор задает `busId` для параметра значение 0, а параметр — значение `chipSelectLine` 0.
    - [Объявление using](../../csharp/whats-new/csharp-8.md#using-declarations) создает экземпляр `SpiDevice` путем вызова `SpiDevice.Create` и передачи `hardwareSpiSettings` . `SpiDevice`Представляет собой ШИНУ SPI. `using`Объявление гарантирует, что объект удален и аппаратные ресурсы освобождаются должным образом.
    - Другое `using` объявление создает экземпляр `Mcp3008` и передает его в `SpiDevice` конструктор.
    - `while`Цикл выполняется бессрочно. Каждая итерация:
        1. Считывает значение CH0 в соединителе ADC путем вызова `mcp.Read(0)` .
        1. Делит значение на 10,24. MCP3008 — это 10-разрядное средство ADC, которое означает, что он возвращает 1024 возможных значений в диапазоне от 0-1023. Деление значения на 10,24 представляет значение в процентах.
        1. Округляет значение до ближайшего целого.
        1. Записывает значение на консоль в формате процента.
        1. Спящий режим 500 мс.

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. Запустите приложение на устройстве Raspberry Pi, перейдя в каталог развертывания и запустив исполняемый файл.

    ```bash
    ./AdcTutorial
    ```

    Обратите внимание на выходные данные при вращении потентиометер набора. Это происходит из-за того, что потентиометер напряжение, передаваемое CH0 в ADC. ADC сравнивает входное напряжение в CH0 со ссылочным напряжением, передаваемым на V<sub>ref</sub> для создания значения.

1. Завершите программу, нажав клавиши <kbd>CTRL + C</kbd>.

Поздравляем! Вы использовали SPI для считывания значений из аналогового в цифровом преобразователе.

## <a name="get-the-source-code"></a>Получение исходного кода

Источник этого руководства [доступен на сайте GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/AdcTutorial).

## <a name="next-steps"></a>Дальнейшие действия

> [!div class="nextstepaction"]
> [Научитесь использовать общего назначения ввода-вывода для мигания индикатора](../tutorials/blink-led.md)
