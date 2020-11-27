---
title: Утверждения и запрет доступа к ресурсам
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], denying access to resources
ms.assetid: 145ebb41-680e-4256-b14c-1efb4af1e982
ms.openlocfilehash: 2c903d5b5aa520b9c79fb8b36912324feaf9a432
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264925"
---
# <a name="claims-and-denying-access-to-resources"></a>Утверждения и запрет доступа к ресурсам

Windows Communication Foundation (WCF) поддерживает механизм авторизации на основе утверждений. Системы могут предоставлять доступ к ресурсам на основе утверждений или отказывать в доступе к ресурсам на основе утверждений. Такие системы должны сначала проверять контекст <xref:System.IdentityModel.Policy.AuthorizationContext> на наличие утверждений, запрещающих доступ, а лишь затем - на наличие утверждений, разрешающих доступ.  
  
 Например, система может отказать в доступе к ресурсу всем пользователям, имеющим утверждение типа `Age`, право <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> и значение ресурса `Under 21`, если для данного удостоверения также имеется утверждение типа `Name`, право <xref:System.IdentityModel.Claims.Rights.Identity%2A> и значение ресурса `Mallory`. Иными словами, система отказывает в доступе пользователям младше 21 года и предоставляет доступ пользователю с именем Mallory. Для правильно реализации такой семантики важно сначала проверять утверждение `Age`, чтобы определить, что пользователю исполнился 21 год. В противном случае, если пользователь Мэллори младше 21 года, он получит доступ к ресурсам только на том основании, что он соответствует утверждению `Name`.  
  
## <a name="see-also"></a>См. также

- [Управление утверждениями и авторизацией с помощью модели удостоверения](managing-claims-and-authorization-with-the-identity-model.md)
- [Утверждения и маркеры](claims-and-tokens.md)
