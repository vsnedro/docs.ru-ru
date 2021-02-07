---
description: 'Дополнительные сведения о: <compilers> element'
title: Элемент <compilers>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
ms.openlocfilehash: 6ced6bc81bc7d829ccebab50e0a361985c970f5e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699172"
---
# <a name="compilers-element"></a>Элемент \<compilers>

Контейнер для элементов конфигурации компилятора; содержит ноль или более [\<compiler>](compiler-element.md) элементов.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<compilers>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  

 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<compiler> Элемент](compiler-element.md)|Задает атрибуты конфигурации компилятора для поставщика языка.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<configuration> Элемент](../configuration-element.md)|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|[\<system.codedom> Элемент](system-codedom-element.md)|Задает параметры конфигурации компилятора для доступных поставщиков языков.|  
  
## <a name="remarks"></a>Remarks  

 [\<compilers>](compilers-element.md)Элемент содержит параметры конфигурации компилятора для поставщиков языков на компьютере. Каждый [\<compiler>](compiler-element.md) элемент задает атрибуты конфигурации компилятора для конкретного поставщика языка.  
  
 Платформа .NET Framework определяет начальные параметры компилятора и языка в файле конфигурации компьютера (Machine.config). Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>. С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.  
  
## <a name="configuration-file"></a>Файл конфигурации  

 Этот элемент можно использовать в файле конфигурации компьютера и файле конфигурации приложения.  
  
## <a name="example"></a>Пример  

 В приведенном ниже примере показан типичный элемент конфигурации компилятора.  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler
          language="c#;cs;csharp"
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Схема файла конфигурации](../index.md)
- [Схема параметров поставщика языка и компилятора](index.md)
- [\<compiler> Элемент](compiler-element.md)
