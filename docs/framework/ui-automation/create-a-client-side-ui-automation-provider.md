---
title: Создание поставщика модели автоматизации пользовательского интерфейса на стороне клиента
description: Ознакомьтесь с примером создания поставщика автоматизации пользовательского интерфейса на стороне клиента. В примере реализуется простой поставщик на стороне клиента для окна консоли.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
ms.openlocfilehash: a25966d0f11e409bd4e53f944fc2528360327039
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168469"
---
# <a name="create-a-client-side-ui-automation-provider"></a>Создание поставщика модели автоматизации пользовательского интерфейса на стороне клиента
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе содержится пример кода, демонстрирующий реализацию клиентского поставщика автоматизации пользовательского интерфейса.  
  
## <a name="example"></a>Пример  
 Приведенный ниже пример кода можно встроить в библиотеку динамической компоновки (DLL), которая реализует очень простой поставщик на стороне клиента для окна консоли. Код не имеет никаких полезных функциональных возможностей, он предназначен для демонстрации основных действий по настройке сборки поставщика, которая может быть зарегистрирована клиентским приложением модели автоматизации пользовательского интерфейса.  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о поставщиках автоматизации пользовательского интерфейса](ui-automation-providers-overview.md)
- [Регистрация сборки поставщика на стороне клиента](register-a-client-side-provider-assembly.md)
