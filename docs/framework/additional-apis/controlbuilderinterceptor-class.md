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
# <a name="controlbuilderinterceptor-class"></a><span data-ttu-id="5d48b-102">Класс Контролбуилдеринтерцептор</span><span class="sxs-lookup"><span data-stu-id="5d48b-102">ControlBuilderInterceptor class</span></span>

<span data-ttu-id="5d48b-103">`ControlBuilderInterceptor`Класс позволяет настраивать или контролировать процесс компиляции.</span><span class="sxs-lookup"><span data-stu-id="5d48b-103">The `ControlBuilderInterceptor` class allows the compilation process to be customized or controlled.</span></span>

## <a name="syntax"></a><span data-ttu-id="5d48b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d48b-104">Syntax</span></span>

```csharp
internal class ControlBuilderInterceptor
```

> [!WARNING]
> <span data-ttu-id="5d48b-105">`ControlBuilderInterceptor`Класс является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="5d48b-105">The `ControlBuilderInterceptor` class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="5d48b-106">Как описано в разделе "Примечания", наличие этого типа можно проверить, чтобы определить, существует ли поддержка типа перехватчика.</span><span class="sxs-lookup"><span data-stu-id="5d48b-106">As described in the Remarks section, the existence of this type can be checked to determine whether interceptor type support is present.</span></span> <span data-ttu-id="5d48b-107">Корпорация Майкрософт не поддерживает никакой другой использования этого класса в рабочем приложении при любых обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="5d48b-107">Microsoft does not support any other use of this class in a production application under any circumstance.</span></span>

## <a name="remarks"></a><span data-ttu-id="5d48b-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="5d48b-108">Remarks</span></span>

<span data-ttu-id="5d48b-109">В .NET Framework 2,0 и .NET Framework 3,5 в обновлении за [август 2020](https://portal.msrc.microsoft.com/security-guidance/releasenotedetail/2020-Aug) добавлена поддержка использования типа перехватчика для настройки или управления процессом компиляции.</span><span class="sxs-lookup"><span data-stu-id="5d48b-109">In .NET Framework 2.0 and .NET Framework 3.5, the [August 2020](https://portal.msrc.microsoft.com/security-guidance/releasenotedetail/2020-Aug) updates added support for using an interceptor type to customize or control the compilation process.</span></span> <span data-ttu-id="5d48b-110">Можно определить, существует ли эта поддержка, с помощью <xref:System.Type.GetType?displayProperty=nameWithType> для проверки существования `ControlBuilderInterceptor` типа, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="5d48b-110">You can determine whether this support is present by using <xref:System.Type.GetType?displayProperty=nameWithType> to check the existence of the `ControlBuilderInterceptor` type, as demonstrated in the following code.</span></span>

```csharp
Type type = Type.GetType("System.Web.Compilation.ControlBuilderInterceptor, System.Web, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a");
```

<span data-ttu-id="5d48b-111">Если возвращаемое значение не равно null, то имеется поддержка перехватчика.</span><span class="sxs-lookup"><span data-stu-id="5d48b-111">If the return value is non-null, then interceptor support is present.</span></span> <span data-ttu-id="5d48b-112">Если возвращаемое значение равно `null` или возникает исключение, то обновления 2020 августа не были установлены и поддержка перехватчика отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5d48b-112">If the return value is `null`, or if an exception is thrown, then the August 2020 updates have not been installed, and interceptor support is absent.</span></span>

<span data-ttu-id="5d48b-113">Если имеется поддержка перехватчика, можно записать и зарегистрировать тип перехватчика, который будет взаимодействовать с процессом компиляции точно так же, как и в <xref:System.Web.Compilation.ControlBuilderInterceptor> более поздних версиях .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5d48b-113">If interceptor support is present, you can write and register an interceptor type that will interact with the compilation process in exactly the same way that <xref:System.Web.Compilation.ControlBuilderInterceptor> does on later versions of .NET Framework.</span></span> <span data-ttu-id="5d48b-114">В .NET Framework 2,0 и .NET Framework 3,5 тип перехватчика может быть любым классом, который соответствует следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="5d48b-114">In .NET Framework 2.0 and .NET Framework 3.5, the interceptor type can be any class that meets the following requirements:</span></span>

* <span data-ttu-id="5d48b-115">Имеет открытый конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="5d48b-115">Has a public, parameterless constructor.</span></span>
* <span data-ttu-id="5d48b-116">Содержит открытые нестатические методы с именами `PreControlBuilderInit` и `OnProcessGeneratedCode` , имеющие одинаковую сигнатуру и семантику в <xref:System.Web.Compilation.ControlBuilderInterceptor.PreControlBuilderInit(System.Web.UI.ControlBuilder,System.Web.UI.TemplateParser,System.Web.UI.ControlBuilder,System.Type,System.String,System.String,System.Collections.IDictionary,System.Collections.IDictionary)> качестве <xref:System.Web.Compilation.ControlBuilderInterceptor.OnProcessGeneratedCode(System.Web.UI.ControlBuilder,System.CodeDom.CodeCompileUnit,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeMemberMethod,System.CodeDom.CodeMemberMethod,System.Collections.IDictionary)> методов и, которые существуют в более поздних версиях .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5d48b-116">Has public, non-static methods named `PreControlBuilderInit` and `OnProcessGeneratedCode` that have the same signature and semantics as the <xref:System.Web.Compilation.ControlBuilderInterceptor.PreControlBuilderInit(System.Web.UI.ControlBuilder,System.Web.UI.TemplateParser,System.Web.UI.ControlBuilder,System.Type,System.String,System.String,System.Collections.IDictionary,System.Collections.IDictionary)> and <xref:System.Web.Compilation.ControlBuilderInterceptor.OnProcessGeneratedCode(System.Web.UI.ControlBuilder,System.CodeDom.CodeCompileUnit,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeMemberMethod,System.CodeDom.CodeMemberMethod,System.Collections.IDictionary)> methods, which exist in later versions of .NET Framework.</span></span>

<span data-ttu-id="5d48b-117">Зарегистрируйте тип перехватчика с помощью `aspnet:20ControlBuilderInterceptor` ключа в разделе Параметры приложения ASP.NET ( `<appSettings>` ).</span><span class="sxs-lookup"><span data-stu-id="5d48b-117">Register the interceptor type by using the `aspnet:20ControlBuilderInterceptor` key in ASP.NET application settings (`<appSettings>`).</span></span> <span data-ttu-id="5d48b-118">Этот параметр приложения должен быть указан на компьютере или в файле *web.config* приложения.</span><span class="sxs-lookup"><span data-stu-id="5d48b-118">This application setting must be listed in your computer or application *web.config* file.</span></span> <span data-ttu-id="5d48b-119">Укажите тип перехватчика, используя его имя типа с указанием сборки.</span><span class="sxs-lookup"><span data-stu-id="5d48b-119">Specify the interceptor type by using its assembly-qualified type name.</span></span> <span data-ttu-id="5d48b-120">В следующем примере показано, как зарегистрировать тип перехватчика с именем `Fabrikam.Interceptor` .</span><span class="sxs-lookup"><span data-stu-id="5d48b-120">The following example shows how to register an interceptor type named `Fabrikam.Interceptor`.</span></span>

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

<span data-ttu-id="5d48b-121">При наличии поддержки перехватчика процесс компиляции взаимодействует с перечисленным типом так, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="5d48b-121">When interceptor support is present, the compilation process interacts with the listed type in the manner described above.</span></span> <span data-ttu-id="5d48b-122">Если отсутствует поддержка перехватчика, параметр приложения игнорируется и не действует.</span><span class="sxs-lookup"><span data-stu-id="5d48b-122">When interceptor support is absent, the application setting is ignored and has no effect.</span></span>

## <a name="requirements"></a><span data-ttu-id="5d48b-123">Требования</span><span class="sxs-lookup"><span data-stu-id="5d48b-123">Requirements</span></span>

<span data-ttu-id="5d48b-124">**Пространство имен:** System. Web. Compilation</span><span class="sxs-lookup"><span data-stu-id="5d48b-124">**Namespace:** System.Web.Compilation</span></span>

<span data-ttu-id="5d48b-125">**Сборка:** System. Web (в System.Web.dll)</span><span class="sxs-lookup"><span data-stu-id="5d48b-125">**Assembly:** System.Web (in System.Web.dll)</span></span>

<span data-ttu-id="5d48b-126">**.NET Framework версии:** 3,5, 2,0</span><span class="sxs-lookup"><span data-stu-id="5d48b-126">**.NET Framework versions:** 3.5, 2.0</span></span>
