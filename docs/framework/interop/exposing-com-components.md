---
title: Предоставление клиентам .NET Framework доступа к COM-компонентам
description: Сведения о процессе предоставления клиентам .NET доступа к COM-компонентам. COM-компоненты являются ценными ресурсами для управляемого кода, выступая в качестве бизнес-приложений среднего уровня или изолированных функций.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
ms.openlocfilehash: 459ba7ffed2e4f6c458f89a63b2baa37180d270d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620850"
---
# <a name="exposing-com-components-to-the-net-framework"></a><span data-ttu-id="60597-104">Предоставление клиентам .NET Framework доступа к COM-компонентам</span><span class="sxs-lookup"><span data-stu-id="60597-104">Exposing COM Components to the .NET Framework</span></span>
<span data-ttu-id="60597-105">В этом разделе описывается процесс, в рамках которого существующий COM-компонент предоставляется управляемому коду.</span><span class="sxs-lookup"><span data-stu-id="60597-105">This section summarizes the process needed to expose an existing COM component to managed code.</span></span> <span data-ttu-id="60597-106">Сведения о разработке COM-серверов, которые тесно интегрируются с платформой .NET Framework, см. в разделе [Вопросы разработки для взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="60597-106">For details about writing COM servers that tightly integrate with the .NET Framework, see [Design Considerations for Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span></span>
  
 <span data-ttu-id="60597-107">Существующие COM-компоненты являются ценными ресурсами для управляемого кода, выступая в качестве бизнес-приложений среднего уровня или изолированных функций.</span><span class="sxs-lookup"><span data-stu-id="60597-107">Existing COM components are valuable resources in managed code as middle-tier business applications or as isolated functionality.</span></span> <span data-ttu-id="60597-108">В идеале компонент содержит основную сборку взаимодействия и строго соответствует стандартам программирования модели COM.</span><span class="sxs-lookup"><span data-stu-id="60597-108">An ideal component has a primary interop assembly and conforms tightly to the programming standards imposed by COM.</span></span>  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a><span data-ttu-id="60597-109">Предоставление клиентам .NET Framework доступа к COM-компонентам</span><span class="sxs-lookup"><span data-stu-id="60597-109">To expose COM components to the .NET Framework</span></span>  
  
1. <span data-ttu-id="60597-110">[Импорт библиотеки типов в виде сборки](importing-a-type-library-as-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="60597-110">[Import a type library as an assembly](importing-a-type-library-as-an-assembly.md).</span></span>  
  
     <span data-ttu-id="60597-111">Общеязыковая среда выполнения требует наличия метаданных для всех типов, включая COM-типы.</span><span class="sxs-lookup"><span data-stu-id="60597-111">The common language runtime requires metadata for all types, including COM types.</span></span> <span data-ttu-id="60597-112">Получить сборку, содержащую импортированные COM-типы, в виде метаданных можно несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="60597-112">There are several ways to obtain an assembly containing COM types imported as metadata.</span></span>  
  
2. <span data-ttu-id="60597-113">[Использование типов COM в управляемом коде](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="60597-113">[Use COM types in managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>  
  
     <span data-ttu-id="60597-114">Вы можете проверять COM-типы, активировать экземпляры и вызывать методы COM-объекта так же, как и для любого другого управляемого типа.</span><span class="sxs-lookup"><span data-stu-id="60597-114">You can inspect COM types, activate instances, and invoke methods on the COM object the same way you do for any managed type.</span></span>  
  
3. <span data-ttu-id="60597-115">[Компиляция проекта, использующего взаимодействие](compiling-an-interop-project.md).</span><span class="sxs-lookup"><span data-stu-id="60597-115">[Compile an interop project](compiling-an-interop-project.md).</span></span>  
  
     <span data-ttu-id="60597-116">Windows SDK предоставляет компиляторы для нескольких языков, соответствующих требованиям спецификации общеязыковой среды выполнения (CLS), включая Visual Basic, C# и C++.</span><span class="sxs-lookup"><span data-stu-id="60597-116">The Windows SDK provides compilers for several languages compliant with the Common Language Specification (CLS), including Visual Basic, C#, and C++.</span></span>  
  
4. <span data-ttu-id="60597-117">[Развертывание приложения взаимодействия](deploying-an-interop-application.md).</span><span class="sxs-lookup"><span data-stu-id="60597-117">[Deploy an interop application](deploying-an-interop-application.md).</span></span>  
  
     <span data-ttu-id="60597-118">Приложения взаимодействия рекомендуется развертывать в виде подписанных сборок со [строгими именами](../../standard/assembly/strong-named.md) в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="60597-118">Interop applications are best deployed as [strong-named](../../standard/assembly/strong-named.md), signed assemblies in the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60597-119">См. также</span><span class="sxs-lookup"><span data-stu-id="60597-119">See also</span></span>

- [<span data-ttu-id="60597-120">Взаимодействие с неуправляемым кодом</span><span class="sxs-lookup"><span data-stu-id="60597-120">Interoperating with Unmanaged Code</span></span>](index.md)
- <span data-ttu-id="60597-121">[Вопросы разработки для взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="60597-121">[Design Considerations for Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span></span>
- [<span data-ttu-id="60597-122">Пример COM-взаимодействия. Клиент .NET и COM-сервер</span><span class="sxs-lookup"><span data-stu-id="60597-122">COM Interop Sample: .NET Client and COM Server</span></span>](com-interop-sample-net-client-and-com-server.md)
- [<span data-ttu-id="60597-123">Независимость от языка и независимые от языка компоненты</span><span class="sxs-lookup"><span data-stu-id="60597-123">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="60597-124">Gacutil.exe (программа глобального кэша сборок)</span><span class="sxs-lookup"><span data-stu-id="60597-124">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
