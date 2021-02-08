---
description: 'Дополнительные сведения: <tokenReplayDetection>'
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a8a6b754a3282afe4f2932296b06b84c09fb6f1a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786542"
---
# \<tokenReplayDetection>

Включает обнаружение воспроизведения маркеров и задает срок действия токенов.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a>Тип  

 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|Включено|Значение типа, указывающее, включено ли обнаружение воспроизведения маркеров. значение true, чтобы включить обнаружение воспроизведения маркеров.|  
|експиратионпериод|Значение типа <xref:System.TimeSpan> , указывающее максимальное количество времени, по истечении которого элемент считается просроченным и удаляется из кэша.  Дополнительные сведения об указании <xref:System.TimeSpan> значений см. в разделе [значения TimeSpan](../windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  

 None  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Задает параметры удостоверений уровня службы.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.|  
  
## <a name="remarks"></a>Remarks  

 `<tokenReplayDetection>`Элемент можно указать на уровне службы в `<identityConfiguration>` элементе или на уровне коллекции обработчика маркеров безопасности под `<securityTokenHandlerConfiguration>` элементом. Параметры коллекции обработчиков маркеров переопределяют указанные в службе.  
  
 Тип кэша воспроизведения токенов задается [\<tokenReplayCache>](tokenreplaycache.md) элементом.
