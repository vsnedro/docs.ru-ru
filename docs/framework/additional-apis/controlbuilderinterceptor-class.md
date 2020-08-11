---
title: Класс Контролбуилдеринтерцептор
ms.date: 08/11/2020
api_name:
- System.Web.Compilation.ControlBuilderInterceptor
api_location:
- System.Web.dll
api_type:
- Assembly
topic_type:
- apiref
ms.openlocfilehash: 312d977f832d262b1bebc6638280b67b133babdf
ms.sourcegitcommit: 70d6a7e4f7187cbfa332f0f8be76566f7828cfcd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2020
ms.locfileid: "88084410"
---
# <a name="controlbuilderinterceptor-class"></a>Класс Контролбуилдеринтерцептор

`ControlBuilderInterceptor`Класс позволяет настраивать или контролировать процесс компиляции.

## <a name="syntax"></a>Синтаксис

```csharp
internal class ControlBuilderInterceptor
```

> [!WARNING]
> `ControlBuilderInterceptor`Класс является внутренним и не предназначен для непосредственного использования в коде.
>
> Как описано в разделе "Примечания", наличие этого типа можно проверить, чтобы определить, существует ли поддержка типа перехватчика. Корпорация Майкрософт не поддерживает никакой другой использования этого класса в рабочем приложении при любых обстоятельствах.

## <a name="remarks"></a>Remarks

В .NET Framework 2,0 и .NET Framework 3,5 в обновлении за [август 2020](https://portal.msrc.microsoft.com/security-guidance/releasenotedetail/2020-Aug) добавлена поддержка использования типа перехватчика для настройки или управления процессом компиляции. Можно определить, существует ли эта поддержка, с помощью <xref:System.Type.GetType?displayProperty=nameWithType> для проверки существования `ControlBuilderInterceptor` типа, как показано в следующем коде.

```csharp
Type type = Type.GetType("System.Web.Compilation.ControlBuilderInterceptor, System.Web, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a");
```

Если возвращаемое значение не равно null, то имеется поддержка перехватчика. Если возвращаемое значение равно `null` или возникает исключение, то обновления 2020 августа не были установлены и поддержка перехватчика отсутствует.

Если имеется поддержка перехватчика, можно записать и зарегистрировать тип перехватчика, который будет взаимодействовать с процессом компиляции точно так же, как и в <xref:System.Web.Compilation.ControlBuilderInterceptor> более поздних версиях .NET Framework. В .NET Framework 2,0 и .NET Framework 3,5 тип перехватчика может быть любым классом, который соответствует следующим требованиям:

* Имеет открытый конструктор без параметров.
* Содержит открытые нестатические методы с именами `PreControlBuilderInit` и `OnProcessGeneratedCode` , имеющие одинаковую сигнатуру и семантику в <xref:System.Web.Compilation.ControlBuilderInterceptor.PreControlBuilderInit(System.Web.UI.ControlBuilder,System.Web.UI.TemplateParser,System.Web.UI.ControlBuilder,System.Type,System.String,System.String,System.Collections.IDictionary,System.Collections.IDictionary)> качестве <xref:System.Web.Compilation.ControlBuilderInterceptor.OnProcessGeneratedCode(System.Web.UI.ControlBuilder,System.CodeDom.CodeCompileUnit,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeMemberMethod,System.CodeDom.CodeMemberMethod,System.Collections.IDictionary)> методов и, которые существуют в более поздних версиях .NET Framework.

Зарегистрируйте тип перехватчика с помощью `aspnet:20ControlBuilderInterceptor` ключа в разделе Параметры приложения ASP.NET ( `<appSettings>` ). Этот параметр приложения должен быть указан на компьютере или в файле *web.config* приложения. Укажите тип перехватчика, используя его имя типа с указанием сборки. В следующем примере показано, как зарегистрировать тип перехватчика с именем `Fabrikam.Interceptor` .

```xml
<configuration>
  ...
  <appSettings>
    ...
    <add key="aspnet:20ControlBuilderInterceptor"
         value="Fabrikam.Interceptor, Fabrikam, Version=1.0.0.0, Culture=neutral, PublicKeyToken=2b3831f2f2b744f7" />
  </appSettings>
</configuration>

To retrieve the assembly-qualified name of a type, use the <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType> property, as demonstrated in the following code.

```csharp
string assemblyQualifiedName = typeof(Fabrikam.Interceptor).AssemblyQualifiedName;
```

При наличии поддержки перехватчика процесс компиляции взаимодействует с перечисленным типом так, как описано выше. Если отсутствует поддержка перехватчика, параметр приложения игнорируется и не действует.

## <a name="requirements"></a>Требования

**Пространство имен:** System. Web. Compilation

**Сборка:** System. Web (в System.Web.dll)

**.NET Framework версии:** 3,5, 2,0
