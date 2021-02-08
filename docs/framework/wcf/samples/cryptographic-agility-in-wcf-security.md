---
description: 'Подробнее: гибкость шифрования в безопасности WCF'
title: Гибкость шифрования в безопасности WCF
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: ab46034b16a846f7399220480fc928655d931be0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778351"
---
# <a name="cryptographic-agility-in-wcf-security"></a>Гибкость шифрования в безопасности WCF

В этом примере показано, как указать в стандартном или пользовательском алгоритме, чтобы обеспечить динамическую реализацию в клиенте Windows Communication Foundation (WCF) и службе. Образец состоит из следующих проектов.

**Служба**

Это автономная служба WCF, которая реализует `ICalculator` интерфейс и защищает конечную точку с помощью <xref:System.ServiceModel.WSHttpBinding> с защищенным сеансом и отключенным надежным сеансом. Служба определяет пользовательский класс `SecurityAlgorithmSuite`, который задает алгоритмы шифрования, используемые для защиты сообщений.

**Клиент**

Это клиент WCF, который обращается к службе после успешной проверки подлинности. Он вызывает операции, предоставляемые интерфейсом `ICalculator` и реализуемые службой. Клиент также определяет тот же пользовательский класс `SecurityAlgorithmSuite`, который задает алгоритмы шифрования, используемые для защиты сообщений.

## <a name="to-use-this-sample"></a>Использование этого образца

1. Откройте решение Криптоагилити. sln в Visual Studio 2012.

2. Чтобы построить решение, нажмите CTRL+SHIFT+B.

3. Откройте проводник и перейдите в каталог \Вкф\басик\секурити\криптоагилити\сервице\бин и запустите файл service.exe с правами администратора, щелкнув правой кнопкой мыши service.exe и выбрав **Запуск от имени администратора**.

4. Перейдите в каталог \WCF\Basic\Security\CryptoAgility\Client\bin и запустите файл client.exe обычным образом.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для платформа .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`

## <a name="see-also"></a>См. также

- [Безопасность Windows Communication Foundation](../feature-details/security.md)
