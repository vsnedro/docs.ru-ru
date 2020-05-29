---
title: Практическое руководство. Загрузка и выгрузка сборок
description: Среда CLR автоматически загружает сборки .NET, на которые ссылается программа. Вы также можете динамически загружать определенные сборки в текущий домен приложения.
ms.date: 08/19/2019
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
ms.openlocfilehash: e6f1ede055dd3f68bced4eba527b2fc65f7d5715
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378684"
---
# <a name="how-to-load-and-unload-assemblies"></a>Практическое руководство. Загрузка и выгрузка сборок
Сборки, на которые ссылается программа, загружаются автоматически средой CLR, но в текущий домен приложения можно также динамически загрузить конкретные сборки. Дополнительные сведения см. в разделе [Практическое руководство. Загрузка сборок в домен приложения](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).

В .NET Framework отдельную сборку невозможно выгрузить, не выгрузив все домены приложений, в которых она содержится. Даже если сборка не входит в область, фактический файл сборки остается загруженным до тех пор, пока не будут выгружены домены приложений с этой сборкой. В .NET Core класс <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> обрабатывает выгрузку сборок. Дополнительные сведения см. в разделе [Использование и отладка сборок с возможностью выгрузки в .NET Core](unloadability.md).

## <a name="load-and-unload-assemblies"></a>Загрузка и выгрузка сборок

Для загрузки сборки в домен приложения используйте один из нескольких методов загрузки, содержащихся в классах <xref:System.AppDomain> и <xref:System.Reflection.Assembly>. Дополнительные сведения см. в разделе [Практическое руководство. Загрузка сборок в домен приложения](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md). Обратите внимание, что .NET Core поддерживает только один домен приложения.

Чтобы выгрузить сборку в .NET Framework, нужно выгрузить все домены приложений, содержащие ее. Чтобы выгрузить домен приложения, используйте метод <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [Практическое руководство. Выгрузка домена приложения](../../framework/app-domains/how-to-unload-an-application-domain.md).

Если нужно выгрузить только часть сборок в приложении .NET Framework, создайте новый домен приложения, выполните код внутри этого домена, а затем выгрузите этот домен приложения. Дополнительные сведения см. в разделе [Практическое руководство. Выгрузка домена приложения](../../framework/app-domains/how-to-unload-an-application-domain.md).  

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../csharp/programming-guide/index.md)
- [Основные понятия программирования (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
- [Сборки в .NET](index.md)
- [Практическое руководство. Загрузка сборок в домен приложения](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
