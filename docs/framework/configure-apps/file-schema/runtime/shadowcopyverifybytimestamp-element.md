---
description: 'Дополнительные сведения о: <shadowCopyVerifyByTimestamp> element'
title: Элемент <shadowCopyVerifyByTimestamp>
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
ms.openlocfilehash: 273bf4c5b01b300cfd564de4ee29c402c6f3e7ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740097"
---
# <a name="shadowcopyverifybytimestamp-element"></a>Элемент \<shadowCopyVerifyByTimestamp>

Указывает, использует ли теневое копирование поведение при запуске по умолчанию, представленное в платформа .NET Framework 4, или возвращается к поведению при запуске более ранних версий платформа .NET Framework.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<shadowCopyVerifyByTimestamp>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|Включено|Обязательный атрибут.<br /><br /> Указывает, были ли домены приложений, использующие теневое копирование, сравниваются метки времени сборки при запуске, чтобы определить, обновлена ли сборка перед теневым копированием сборки.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|Да|При запуске копирует только сборки, которые были обновлены с момента последнего копирования в каталог теневых копий. Это значение по умолчанию для платформа .NET Framework 4.|  
|false|Восстанавливает поведение при запуске предыдущих версий платформа .NET Framework, при запуске которого были скопированы все файлы.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Remarks  

 Начиная с платформа .NET Framework 4 сборки копируются только в том случае, если их метки времени указывают, что они изменились с момента последнего копирования в каталог теневых копий. Это улучшает время запуска для многих приложений, использующих теневое копирование, как описано в разделе [теневое копирование сборок](../../../app-domains/shadow-copy-assemblies.md). Для приложений с большим процентом и высокой частотой обновления сборок это изменение в поведении может не быть выгодно. В этом случае можно использовать этот элемент для восстановления поведения предыдущих версий платформы .NET Framework.  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как отключить поведение при запуске теневого копирования по умолчанию в платформа .NET Framework 4 и вернуться к режиму запуска предыдущих версий платформа .NET Framework.  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Теневое копирование сборок](../../../app-domains/shadow-copy-assemblies.md)
