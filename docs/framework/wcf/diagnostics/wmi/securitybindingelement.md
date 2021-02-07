---
description: 'Дополнительные сведения о: SecurityBindingElement'
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
ms.openlocfilehash: bc9a519978a9cccccd80a58abb8d109fa9bc9337
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743815"
---
# <a name="securitybindingelement"></a>SecurityBindingElement

SecurityBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс SecurityBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс SecurityBindingElement имеет следующие свойства.  
  
### <a name="defaultalgorithmsuite"></a>DefaultAlgorithmSuite  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Задает алгоритмы, используемые в сочетании с привязкой.  
  
### <a name="includetimestamp"></a>IncludeTimestamp  

 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, указывающее, будет ли в каждое сообщение вноситься метка времени.  
  
### <a name="keyentropymode"></a>KeyEntropyMode  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Источник энтропии, используемый для создания ключей.  
  
### <a name="localservicesecuritysettings"></a>LocalServiceSecuritySettings  

 Тип данных: LocalServiceSecuritySettings  
  
 Тип доступа: только для чтения  
  
 Свойства безопасности для локальной службы, соответствующие данной привязке.  
  
### <a name="messagesecurityversion"></a>MessageSecurityVersion  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Версия, используемая для безопасности сообщения.  
  
### <a name="securityheaderlayout"></a>SecurityHeaderLayout  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Порядок элементов в заголовке безопасности для данной привязки.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
