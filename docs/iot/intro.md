---
title: Разработка приложений для устройств IoT с помощью библиотек .NET IoT
description: Узнайте, как можно использовать .NET для создания приложений для устройств и сценариев Интернета вещей.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: overview
ms.prod: dotnet
ms.openlocfilehash: c3d05ec5b05780f91404c3c27e91bcd602b0faeb
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2020
ms.locfileid: "96594029"
---
# <a name="develop-apps-for-iot-devices-with-the-net-iot-libraries"></a>Разработка приложений для устройств IoT с помощью библиотек .NET IoT

.NET работает на различных платформах и архитектурах. Поддерживаются стандартные доски Интернета вещей (IoT), такие как Raspberry Pi и Хуммингбоард. Приложения IoT обычно взаимодействуют со специализированным оборудованием, например датчиками, аналоговыми и цифровыми преобразователями, а также ЖК-устройствами. Эти сценарии включены в библиотеках .NET IoT.

## <a name="video-overview"></a>Видеообзор

<!--markdownlint-disable MD034 -->
> [!VIDEO https://channel9.msdn.com/Series/IoT-101/Intro-to-IOT-with-NET-Core-1-of-9/player]

## <a name="libraries"></a>Библиотеки

Библиотеки .NET IoT состоят из двух пакетов NuGet:

- [System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio/) <span class="docon docon-navigate-external x-hidden-focus"></span>
- [Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings/) <span class="docon docon-navigate-external x-hidden-focus"></span>

### <a name="systemdevicegpio"></a>System.Device.Gpio

`System.Device.Gpio` поддерживает различные протоколы для взаимодействия с аппаратными креплениями низкого уровня для управления устройствами. приведенные ниже.

- Универсальный ввод-вывод (GPIO)
- Канал Inter-Integrated (I2C)
- Интерфейс Serial периферийных устройств (SPI)
- Модуляция ширины импульса (ШИРОТы)
- Последовательный порт

### <a name="iotdevicebindings"></a>Iot.Device.Bindings

`Iot.Device.Bindings`Пакет:

* Содержит [привязки устройств](https://github.com/dotnet/iot/blob/master/src/devices/README.md) <span class="docon docon-navigate-external x-hidden-focus"></span> для упрощения разработки приложений с помощью оболочки System. Device. GPIO.
* Поддерживается сообществом, а дополнительные привязки постоянно добавляются.

К часто используемым привязкам устройств относятся:

- [Чарактерлкд — отображение символов LCD](https://github.com/dotnet/iot/tree/master/src/devices/CharacterLcd)<span class="docon docon-navigate-external x-hidden-focus"></span>
- [SN74HC595-8-разрядный сдвиг регистра](https://github.com/dotnet/iot/tree/master/src/devices/Sn74hc595)<span class="docon docon-navigate-external x-hidden-focus"></span>
- [BrickPi3](https://github.com/dotnet/iot/tree/master/src/devices/BrickPi3)<span class="docon docon-navigate-external x-hidden-focus"></span>
- [Драйвер матрицы Max7219-LED](https://github.com/dotnet/iot/tree/master/src/devices/Max7219)<span class="docon docon-navigate-external x-hidden-focus"></span>
- [Ргбледматрикс-матрица индикаторов RGB](https://github.com/dotnet/iot/tree/master/src/devices/RGBLedMatrix)<span class="docon docon-navigate-external x-hidden-focus"></span>

## <a name="supported-operating-systems"></a>Поддерживаемые операционные системы

`System.Device.Gpio` поддерживается в большинстве версий Linux, поддерживающих ARM/ARM64 и Windows 10 IoT Core.

> [!TIP]
> Для Raspberry Pi рекомендуется [Raspberry Pi OS](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) <span class="docon docon-navigate-external x-hidden-focus"></span> (прежнее название — Raspbian).  

## <a name="supported-hardware-platforms"></a>Поддерживаемые аппаратные платформы

`System.Device.Gpio` совместима с большинством одноплатных платформ. Рекомендуемые платформы — Raspberry Pi (2 и выше) и Хуммингбоард. Другие платформы, совместимые с совместимостью, — это Беаглебоард и ОДРОИД.

Платформы PC поддерживаются посредством использования моста USB и SPI/I2C.

> [!IMPORTANT]
> Платформа .NET не поддерживается на устройствах архитектуры ARMv6, включая нуль-и Raspberry Pi устройств Raspberry Pi до Raspberry Pi 2.

## <a name="resources"></a>Ресурсы

- [Библиотеки .NET IOT на GitHub](https://github.com/dotnet/iot)<span class="docon docon-navigate-external x-hidden-focus"></span>
