---
title: Регистрация сборки поставщика на стороне клиента
description: Ознакомьтесь с примером, в котором показано, как зарегистрировать библиотеку DLL, содержащую поставщики автоматизации пользовательского интерфейса на стороне клиента.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- registering client-side provider assemblies
- client-side provider assemblies, registering
- UI Automation, registering provider assemblies
- provider assemblies, registering
ms.assetid: a03af4d9-2771-43cc-b07b-d468dca23190
ms.openlocfilehash: 034a109bb69c08883c0943b7b6ef69a397a8e7e1
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168133"
---
# <a name="register-a-client-side-provider-assembly"></a><span data-ttu-id="b94ae-103">Регистрация сборки поставщика на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="b94ae-103">Register a Client-Side Provider Assembly</span></span>
> [!NOTE]
> <span data-ttu-id="b94ae-104">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="b94ae-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="b94ae-105">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="b94ae-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="b94ae-106">В этом разделе показано, как зарегистрировать библиотеку DLL, содержащую поставщики автоматизации пользовательского интерфейса на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="b94ae-106">This topic shows how to register a DLL that contains client-side UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b94ae-107">Пример</span><span class="sxs-lookup"><span data-stu-id="b94ae-107">Example</span></span>  
 <span data-ttu-id="b94ae-108">В следующем примере показано, как зарегистрировать сборку, содержащую поставщик для окна консоли.</span><span class="sxs-lookup"><span data-stu-id="b94ae-108">The following example shows how to register an assembly that contains a provider for a console window.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSClientProgram.cs#102)]
 [!code-vb[UIAClientSideProvider_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csclientprogram.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="b94ae-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b94ae-109">See also</span></span>

- [<span data-ttu-id="b94ae-110">Создание поставщика модели автоматизации пользовательского интерфейса на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="b94ae-110">Create a Client-Side UI Automation Provider</span></span>](create-a-client-side-ui-automation-provider.md)
