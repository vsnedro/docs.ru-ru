---
description: 'Дополнительные сведения: 1004-Воркфловинстанцеабортед'
title: 1004 ― WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: 4aaa0899da9b0b8510684a13537a8cb8f9117ee1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755626"
---
# <a name="1004---workflowinstanceaborted"></a>1004 ― WorkflowInstanceAborted

## <a name="properties"></a>Свойства

|||
|-|-|
|ID|1004|
|Keywords|WFRuntime|
|Уровень|Сведения|
|Канал|Microsoft-Windows-Application Server-Applications/Debug|

## <a name="description"></a>Описание

Указывает, что экземпляр рабочего процесса прерван с исключением.

## <a name="message"></a>Сообщение

Выполнение элемента WorkflowInstance с идентификатором «%1» было прервано в результате исключения.

## <a name="details"></a>Сведения

|Имя элемента данных|Тип элемента данных|Описание|
|--------------------|--------------------|-----------------|
|WorkflowInstanceId|`xs:string`|Идентификатор экземпляра для рабочего процесса.|
|Исключение|`xs:string`|Сведения об исключении|
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
