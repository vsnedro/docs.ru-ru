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
ms.openlocfilehash: 1d3fb53775a4d88f9372b582189a38e18376761a
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855820"
---
# <a name="dangerous-permissions-and-policy-administration"></a>Опасные разрешения и администрирование политик

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

Некоторые из защищенных операций, для которых .NET Framework предоставляет разрешения, потенциально могут позволить обойти систему безопасности. Эти небезопасные разрешения должны предоставляться только надежному коду и только в случае необходимости. Обычно невозможно защититься от вредоносного кода, который получил эти разрешения.  
  
> [!NOTE]
> В .NET Framework 4 были внесены важные изменения в модель и терминологию безопасности .NET Framework. Дополнительные сведения об этих изменениях см. в разделе [изменения в системе безопасности](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Правила написания безопасного кода](../../standard/security/secure-coding-guidelines.md)
