---
title: Практическое руководство. Создание домена приложения
description: Узнайте о том, как создать домен приложения в .NET. Вы можете создать домен приложения, чтобы загрузить сборки и управлять ими лично, или создать сборку для выполнения кода.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
ms.openlocfilehash: 8e44e682f64854dbc0181b26f6ed3fa2905b7814
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104802"
---
# <a name="how-to-create-an-application-domain"></a>Практическое руководство. Создание домена приложения
Хост-приложение CLR автоматически создает домены приложений в нужный момент. Но можно создать собственные домены приложений и загрузить их в те сборки, которыми требуется управлять отдельно. Кроме того, домены приложений можно создать из доменов, выполняющих код.  
  
 Создать домен приложения можно с помощью одного из перегруженных методов **CreateDomain** в классе <xref:System.AppDomain?displayProperty=nameWithType>. Для домена приложения можно назначить имя и использовать его в ссылках на домен.  
  
 В следующем примере создается новый домен приложения, которому назначается имя `MyDomain`, после чего на консоль выводятся имя основного домена и нового созданного дочернего домена приложения.  
  
## <a name="example"></a>Пример  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## <a name="see-also"></a>См. также

- [Программирование с использованием доменов приложений](application-domains.md#programming-with-application-domains)
- [Использование доменов приложений](use.md)
