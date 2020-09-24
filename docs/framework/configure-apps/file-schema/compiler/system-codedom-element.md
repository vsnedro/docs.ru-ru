---
title: Элемент <system.codedom>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: 6c35e24696be040788a0c44cbb100ebb35d37157
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149573"
---
# <a name="systemcodedom-element"></a>Элемент \<system.codedom>

Задает параметры конфигурации компилятора для доступных поставщиков языков.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.codedom>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  

 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<compilers>](compilers-element.md)|Контейнер для элементов конфигурации компилятора; содержит ноль или более [\<compiler>](compiler-element.md) элементов.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="net-framework-version-20"></a>.NET Framework версии 2,0  

 [\<system.codedom>](system-codedom-element.md)Элемент содержит параметры конфигурации компилятора для поставщиков языков, установленных на компьютере в дополнение к поставщикам по умолчанию, которые устанавливаются вместе с .NET Framework, например <xref:Microsoft.CSharp.CSharpCodeProvider> и <xref:Microsoft.VisualBasic.VBCodeProvider> . [\<compilers>](compilers-element.md)Элемент содержит ноль или более [\<compiler>](compiler-element.md) элементов. Каждый [\<compiler>](compiler-element.md) элемент задает атрибуты конфигурации компилятора для конкретного поставщика языка.  
  
 Разработчики и поставщики компиляторов могут добавлять параметры конфигурации в файл конфигурации компьютера (Machine.config) для новой <xref:System.CodeDom.Compiler.CodeDomProvider> реализации. Используйте <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> метод для программного перечисления поставщиков языка по умолчанию и поставщиков языков, определенных параметрами конфигурации компилятора на компьютере.  
  
> [!NOTE]
> В .NET Framework версиях 1,0 и 1,1 поставщики языка по умолчанию, предоставляемые .NET Framework, идентифицируются в [\<compilers>](compilers-element.md) элементе. В .NET Framework версии 2,0 поставщики языка по умолчанию не определяются в [\<compilers>](compilers-element.md) элементе, но их можно перечислить с помощью <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> метода.  
  
## <a name="net-framework-versions-10-and-11"></a>.NET Framework версии 1,0 и 1,1  

 [\<system.codedom>](system-codedom-element.md)Элемент содержит параметры конфигурации компилятора для поставщиков языков на компьютере. [\<compilers>](compilers-element.md)Элемент содержит ноль или более [\<compiler>](compiler-element.md) элементов. Каждый [\<compiler>](compiler-element.md) элемент задает атрибуты конфигурации компилятора для конкретного поставщика языка.  
  
 В .NET Framework начальные параметры компилятора определены файле конфигурации компьютера (Machine.config). Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>. С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.  
  
## <a name="configuration-file"></a>Файл конфигурации  

 Этот элемент можно использовать в файле конфигурации компьютера и файле конфигурации приложения.  
  
## <a name="example"></a>Пример  

 В следующем примере показана типичная конфигурация компилятора.  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,
          Version=1.0.5000.0, Culture=neutral,
          PublicKeyToken=b77a5c561934e089"  
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
- [Схема параметров поставщиков языков и компиляторов](index.md)
- [\<compiler> Элемент](compiler-element.md)
