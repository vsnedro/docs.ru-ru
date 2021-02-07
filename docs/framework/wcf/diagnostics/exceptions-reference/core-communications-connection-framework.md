---
description: 'Дополнительные сведения: основные коммуникации: инфраструктура подключений'
title: 'Основное взаимодействие: структура подключений'
ms.date: 03/30/2017
ms.assetid: 61ee00e1-896d-47c8-942f-1db28ac89cdc
ms.openlocfilehash: c0603f6f47c6259faeb2de4e9fc6c1be37bbb183
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686561"
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
