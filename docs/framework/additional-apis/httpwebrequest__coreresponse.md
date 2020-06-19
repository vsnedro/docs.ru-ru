---
title: HttpWebRequest. _CoreResponse поле
description: Прочитайте о поле HttpWebRequest. _CoreResponse в .NET. Это поле является объектом Коререспонседата или Exception, содержащим результат синтаксического анализа ответа HTTP.
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 5093ec7ed2c3b94931dcd622ae9ccdb42feffa18
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989754"
---
# <a name="httpwebrequest_coreresponse-field"></a>HttpWebRequest. \_ Поле Коререспонсе

`HttpWebRequest._CoreResponse`— Это объект ( [коререспонседата](coreresponsedata.md) или <xref:System.Exception> ), содержащий результат синтаксического анализа ответа HTTP.

## <a name="syntax"></a>Синтаксис
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> Этот API не предназначен для непосредственного использования в коде. Вместо этого следует использовать <xref:System.Diagnostics.DiagnosticSource> для подключения сетевого кода. Ознакомьтесь с [руководством пользователя DiagnosticSource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
>
> Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Система (в System.dll)

**.NET Framework версии:** Доступно с 2,0.
