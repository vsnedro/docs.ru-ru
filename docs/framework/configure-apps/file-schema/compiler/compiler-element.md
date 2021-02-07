---
description: 'Дополнительные сведения о: <compiler> element'
title: Элемент <compiler>
ms.date: 08/14/2018
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
ms.openlocfilehash: 91540d2217320b225ae67a48d616720ef2a0b679
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699224"
---
# <a name="compiler-element"></a>Элемент \<compiler>

Задает атрибуты конфигурации компилятора для поставщика языка.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compiler>**

## <a name="syntax"></a>Синтаксис

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`compilerOptions`|Необязательный атрибут.<br /><br /> Задает дополнительные зависящие от компилятора аргументы для компиляции. Значения для `compilerOptions` атрибута обычно перечислены в разделе параметров компилятора для компилятора.|
|`extension`|Обязательный атрибут.<br /><br /> Предоставляет разделенный точками с запятой список расширений имен файлов, используемых исходными файлами для поставщика языка. Например, ".cs".|
|`language`|Обязательный атрибут.<br /><br /> Предоставляет разделенный точками с запятой список имен языков, поддерживаемых поставщиком языка. Например, "C#;cs;csharp".|
|`type`|Обязательный атрибут.<br /><br /> Указывает имя типа поставщика языка, включая имя сборки, содержащей реализацию поставщика. Имя типа должно соответствовать требованиям, определенным при [указании полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|
|`warningLevel`|Необязательный атрибут.<br /><br /> Задает уровень предупреждений компилятора по умолчанию. Определяет уровень, на котором поставщик языка рассматривает предупреждения компиляции как ошибки.|

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<providerOption> Элемент](provideroption-element.md)|Указывает атрибуты версии компилятора для поставщика языка.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<configuration> Элемент](../configuration-element.md)|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|[\<system.codedom> Элемент](system-codedom-element.md)|Задает параметры конфигурации компилятора для доступных поставщиков языков.|
|[\<compilers> Элемент](compilers-element.md)|Контейнер для элементов конфигурации компилятора; содержит ноль или более `<compiler>` элементов.|

## <a name="remarks"></a>Remarks

Каждый `<compiler>` элемент задает атрибуты конфигурации компилятора для конкретного поставщика языка. Поставщик расширяет <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> класс для конкретного языка; `<compiler>` элемент определяет параметры компилятора и генератора кода для поставщика языка.

В .NET Framework начальные параметры компилятора определены файле конфигурации компьютера (Machine.config). Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>. С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.

Элементы компилятора в файле приложения или веб-конфигурации могут дополнять или переопределять параметры в файле конфигурации компьютера. Если для одного и того же имени языка или одного расширения файла настроено несколько реализаций поставщика, последняя конфигурация сопоставления переопределяет все предыдущие настроенные поставщики для этого имени языка или расширения файла.

## <a name="configuration-file"></a>Файл конфигурации

Этот элемент можно использовать в файле конфигурации компьютера и файле конфигурации приложения.

## <a name="example"></a>Пример

В следующем примере показан типичный элемент конфигурации компилятора:

```xml
<configuration>
  <system.codedom>
    <compilers>
      <!-- zero or more compiler elements -->
      <compiler
        language="c#;cs;csharp"
        extension=".cs"
        type="Microsoft.CSharp.CSharpCodeProvider, System,
          Version=2.0.3600.0, Culture=neutral,
          PublicKeyToken=b77a5c561934e089"
        compilerOptions="/optimize"
        warningLevel="1" />
    </compilers>
  </system.codedom>
</configuration>
```

## <a name="see-also"></a>См. также

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Схема файла конфигурации](../index.md)
- [\<compilers> Элемент](compilers-element.md)
- [Указание полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [Элемент compiler для элемента compilers для элемента compilation (схема параметров ASP.NET)](/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
