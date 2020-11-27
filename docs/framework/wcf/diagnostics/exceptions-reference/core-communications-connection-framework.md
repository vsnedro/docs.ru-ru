---
title: 'Основное взаимодействие: структура подключений'
ms.date: 03/30/2017
ms.assetid: 61ee00e1-896d-47c8-942f-1db28ac89cdc
ms.openlocfilehash: bd90bf75370776382b584388330e59a0701ed772
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96277508"
---
# <a name="core-communications-connection-framework"></a>Основное взаимодействие: структура подключений

В этом разделе перечислены все исключения, созданные платформой подключений Windows Communication Foundation (WCF).  
  
## <a name="exception-list"></a>Список исключений  
  
|Код ресурса|Строка ресурса|  
|-------------------|---------------------|  
|CloseTimedOut|Срок ожидания метода Close истек по прошествии заданного времени. Увеличьте время ожидания, передаваемое вызову метода Close, или увеличьте значение CloseTimeout в привязке. Возможно, выделенное для этой операции время было частью более длительного времени ожидания.|  
|ContentTypeMismatch|Указанный тип контента был отправлен службе, которая ожидала указанный. Возможно несоответствие привязок клиента и службы.|  
|DuplexChannelAbortedDuringOpen|Дуплексный канал к указанному был закрыт во время процесса Open.|  
|FramingValueNotAvailable|Доступ к значению невозможен, так как оно не было полностью декодировано.|  
|OperationAbortedDuringConnectionEstablishment|Операция была прервана во время установления подключения к указанному.|  
|ReceiveTimedOut2|Срок ожидания операции получения истек по прошествии заданного времени. Возможно, выделенное для этой операции время было частью более длительного времени ожидания.|  
|SendCannotBeCalledAfterCloseOutputSession|Отправка сообщений по каналу после вызова метода CloseOutputSession невозможна.|
