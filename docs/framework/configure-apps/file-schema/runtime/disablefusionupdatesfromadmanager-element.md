---
description: 'Дополнительные сведения о: <disableFusionUpdatesFromADManager> element'
title: Элемент <disableFusionUpdatesFromADManager>
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
ms.openlocfilehash: c3b5758a12fc78c67ec0a4a9631361808724e72a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787088"
---
# <a name="disablefusionupdatesfromadmanager-element"></a>Элемент \<disableFusionUpdatesFromADManager>

Указывает, отключено ли поведение по умолчанию, которое разрешает хост-приложению среды выполнения переопределять параметры конфигурации для домена приложения.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableFusionUpdatesFromADManager>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|Включено|Обязательный атрибут.<br /><br /> Указывает, отключена ли возможность по умолчанию переопределять параметры Fusion.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|0|Не отключайте возможность переопределения параметров Fusion. Это поведение по умолчанию, начиная с платформа .NET Framework 4.|  
|1|Отключить возможность переопределения параметров Fusion. Это позволяет вернуться к поведению более ранних версий платформа .NET Framework.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Remarks  

 Начиная с платформа .NET Framework 4, поведение по умолчанию заключается в том, чтобы разрешить <xref:System.AppDomainManager> объекту переопределять параметры конфигурации с помощью <xref:System.AppDomainSetup.ConfigurationFile%2A> свойства или <xref:System.AppDomainSetup.SetConfigurationBytes%2A> метода <xref:System.AppDomainSetup> объекта, который передается в вашу реализацию <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> метода, в подкласс <xref:System.AppDomainManager> . Для домена приложения по умолчанию измененные параметры переопределяют параметры, заданные в файле конфигурации приложения. Для других доменов приложений они переопределяют параметры конфигурации, переданные в <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> метод или.  
  
 Можно либо передать новые сведения о конфигурации, либо передать значение null ( `Nothing` в Visual Basic), чтобы исключить переданные конфигурации.  
  
 Не следует передавать сведения о конфигурации как в <xref:System.AppDomainSetup.ConfigurationFile%2A> свойство, так и в <xref:System.AppDomainSetup.SetConfigurationBytes%2A> метод. Если данные о конфигурации передаются в оба значения, то данные, передаваемые в <xref:System.AppDomainSetup.ConfigurationFile%2A> свойство, игнорируются, так как <xref:System.AppDomainSetup.SetConfigurationBytes%2A> метод переопределяет сведения о конфигурации из файла конфигурации приложения. При использовании <xref:System.AppDomainSetup.ConfigurationFile%2A> свойства можно передать значение null ( `Nothing` в Visual Basic) <xref:System.AppDomainSetup.SetConfigurationBytes%2A> методу, чтобы исключить все байты конфигурации, указанные в вызове <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> метода или.  
  
 Помимо сведений о конфигурации, можно изменить следующие параметры <xref:System.AppDomainSetup> объекта, который передается в реализацию <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> метода:,,,,, <xref:System.AppDomainSetup.ApplicationBase%2A> <xref:System.AppDomainSetup.ApplicationName%2A> <xref:System.AppDomainSetup.CachePath%2A> <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A> <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> <xref:System.AppDomainSetup.DisallowCodeDownload%2A> , <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A> , <xref:System.AppDomainSetup.DynamicBase%2A> ,,,, <xref:System.AppDomainSetup.LoaderOptimization%2A> <xref:System.AppDomainSetup.PrivateBinPath%2A> <xref:System.AppDomainSetup.PrivateBinPathProbe%2A> <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> и <xref:System.AppDomainSetup.ShadowCopyFiles%2A> .  
  
 В качестве альтернативы использованию `<disableFusionUpdatesFromADManager>` элемента можно отключить поведение по умолчанию, создав параметр реестра или задав переменную среды. В реестре создайте значение DWORD с именем `COMPLUS_disableFusionUpdatesFromADManager` в разделе `HKCU\Software\Microsoft\.NETFramework` или `HKLM\Software\Microsoft\.NETFramework` и установите значение 1. В командной строке задайте для переменной среды значение `COMPLUS_disableFusionUpdatesFromADManager` 1.  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как отключить возможность переопределения параметров Fusion с помощью `<disableFusionUpdatesFromADManager>` элемента.  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Обнаружение сборок в среде выполнения](../../../deployment/how-the-runtime-locates-assemblies.md)
