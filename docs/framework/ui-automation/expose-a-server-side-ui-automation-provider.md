---
title: Представление поставщика автоматизации пользовательского интерфейса со стороны сервера
description: Просмотрите пример, в котором показано, как предоставить поставщик автоматизации пользовательского интерфейса на стороне сервера, размещенный в окне System. Windows. Forms. Control.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- expose a server-side UI Automation provider
- UI Automation, server-side provider, exposing
- server-side UI Automation provider, exposing
ms.assetid: 55d419c0-2201-4101-90c9-2888df4dbb47
ms.openlocfilehash: be39130c7a91fc081256bf14a87f503d27f45129
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276533"
---
# <a name="expose-a-server-side-ui-automation-provider"></a>Представление поставщика автоматизации пользовательского интерфейса со стороны сервера

> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе содержится пример кода, демонстрирующий предоставление поставщика автоматизации пользовательского интерфейса со стороны сервера, размещенного в окне <xref:System.Windows.Forms.Control?displayProperty=nameWithType> .  
  
 В примере переопределяется процедура окна для перехвата сообщения WM_GETOBJECT, отправляемого основной службой [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , когда клиентское приложение запрашивает информацию об окне.  
  
## <a name="example"></a>Пример  

 [!code-csharp[UIAFragmentProvider_snip#116](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#116)]
 [!code-vb[UIAFragmentProvider_snip#116](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#116)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о поставщиках автоматизации пользовательского интерфейса](ui-automation-providers-overview.md)
- [Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера](server-side-ui-automation-provider-implementation.md)
