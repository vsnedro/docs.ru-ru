---
title: Опасные разрешения и администрирование политик
description: См. ссылки на различные опасные разрешения в .NET. Эти разрешения должны быть предоставлены только доверенному коду и только при необходимости.
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
ms.openlocfilehash: a2f4469590fea38924430b07eaf20d49f4dc46e9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556945"
---
# <a name="dangerous-permissions-and-policy-administration"></a>Опасные разрешения и администрирование политик

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

Некоторые из защищенных операций, для которых .NET Framework предоставляет разрешения, потенциально могут позволить обойти систему безопасности. Эти небезопасные разрешения должны предоставляться только надежному коду и только в случае необходимости. Обычно невозможно защититься от вредоносного кода, который получил эти разрешения.  
  
> [!NOTE]
> В .NET Framework 4 были внесены важные изменения в модель и терминологию безопасности .NET Framework. Дополнительные сведения об этих изменениях см. в разделе [изменения в системе безопасности](/previous-versions/dotnet/framework/security/security-changes).  
  
 Небезопасные разрешения приведены в следующей таблице.  
  
|Разрешение|Потенциальный риск|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|Позволяет управляемому коду вызывать неуправляемый код, который часто небезопасен.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|Без проверки код может что-либо сделать.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|Непроверенное свидетельство может обмануть систему безопасности.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|Возможность изменять политику безопасности может отключить систему безопасности.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|Использование сериализации позволяет обойти механизмы специальных возможностей. Подробные сведения см. в разделе [Безопасность и сериализация](security-and-serialization.md).|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|Возможность установки текущего участника может сбить с толку безопасность на основе ролей.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|Управление потоками представляет опасность, поскольку состояние безопасности связано с потоками.|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|Можно использовать закрытые члены для нарушения правил доступа.|  
  
## <a name="see-also"></a>См. также

- [Правила написания безопасного кода](../../standard/security/secure-coding-guidelines.md)
