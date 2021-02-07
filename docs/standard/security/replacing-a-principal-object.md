---
description: 'Дополнительные сведения: замена объекта Principal'
title: Замена объекта Principal
ms.date: 07/15/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET], replacing principal objects
- security [.NET], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
ms.openlocfilehash: 3f413a3b0824cef9f28454bf109d40556f61c26b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684988"
---
# <a name="replacing-a-principal-object"></a>Замена объекта Principal

Приложения, предоставляющие службы проверки подлинности, должны иметь возможность заменять объект **Principal** (<xref:System.Security.Principal.IPrincipal>) для данного потока. Более того, система безопасности должна защищать возможность замены объектов **Principal** , так как злонамеренно подключенный неправильный **Principal** является угрозой безопасности приложения, предоставляя неверное удостоверение или роль. Таким образом, приложениям, которым требуется возможность замены объектов **Principal** , должен быть предоставлен объект <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> для элемента управления "Участник". (Обратите внимание, что это разрешение не требуется для выполнения проверок безопасности на основе ролей или для создания объектов **Principal** .)  
  
Текущий объект **Principal** можно заменить, выполнив следующие задачи.  
  
1. Создайте замещающий объект **Principal** и связанный объект **Identity** (удостоверение).  
  
2. Подключите новый объект **Principal** к контексту вызова.  
  
## <a name="example"></a>Пример

В следующем примере показывается, как создать универсальный объект Principal и использовать его для задания участника потока.  
  
[!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
[!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>
- [Объекты Principal и Identity](principal-and-identity-objects.md)
- [Безопасность ASP.NET Core](/aspnet/core/security/)
