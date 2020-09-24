---
title: Элемент <assemblyIdentity> для <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
ms.openlocfilehash: f3e74b05ac0fd7c57963f2aad047ba3f2d63a10a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170185"
---
# <a name="assemblyidentity-element-for-runtime"></a>Элемент \<assemblyIdentity> для \<runtime>

Содержит идентифицирующие сведения о сборке.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentity>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
   <assemblyIdentity
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`name`|Обязательный атрибут.<br /><br /> Имя сборки|  
|`culture`|Необязательный атрибут.<br /><br /> Строка, указывающая язык и страну или регион сборки.|  
|`publicKeyToken`|Необязательный атрибут.<br /><br /> Шестнадцатеричное значение, указывающее строгое имя сборки.|  
|`processorArchitecture`|Необязательный атрибут.<br /><br /> Одно из значений "x86", "amd64", "MSIL" или "ia64", определяющее архитектуру процессора для сборки, содержащей код, зависящий от процессора. В значениях регистр не учитывается. Если атрибуту присвоено любое другое значение, весь `<assemblyIdentity>` элемент игнорируется. См. раздел <xref:System.Reflection.ProcessorArchitecture>.|  
  
## <a name="processorarchitecture-attribute"></a>Атрибут processorArchitecture  
  
|Значение|Описание|  
|-----------|-----------------|  
|`amd64`|Только архитектура AMD x86-64.|  
|`ia64`|Только архитектура Intel Itanium.|  
|`msil`|Код нейтрален по отношению к процессору и разрядности слова.|  
|`x86`|32-разрядный процессор x86, либо собственный, либо в среде Windows on Windows (WOW) на 64-разрядной платформе.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`assemblyBinding`|Содержит сведения о перенаправлении версии сборки и о расположениях сборок.|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`dependentAssembly`|Инкапсулирует политику привязки и расположение каждой сборки. `<dependentAssembly>`Для каждой сборки используется один элемент.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Remarks  

 Каждый **\<dependentAssembly>** элемент должен иметь один **\<assemblyIdentity>** дочерний элемент.  
  
 Если `processorArchitecture` атрибут имеется, `<assemblyIdentity>` элемент применяется только к сборке с соответствующей архитектурой процессора. Если `processorArchitecture` атрибут отсутствует, `<assemblyIdentity>` элемент может применяться к сборке с любой архитектурой процессора.  
  
 В следующем примере показан файл конфигурации для двух сборок с одинаковым именем, предназначенных для двух разных архитектур процессора, чьи версии не поддерживали синхронизацию. При выполнении приложения на платформе x86 первый `<assemblyIdentity>` элемент применяется, а другой игнорируется. Если приложение выполняется на платформе, отличной от x86 или ia64, то оба они игнорируются.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Если файл конфигурации содержит элемент без `<assemblyIdentity>` `processorArchitecture` атрибута и не содержит элемент, соответствующий платформе, то используется элемент без `processorArchitecture` атрибута.  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как предоставить сведения о сборке.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Перенаправление версий сборки](../../redirect-assembly-versions.md)
