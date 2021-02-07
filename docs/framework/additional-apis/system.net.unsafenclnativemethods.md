---
description: 'Дополнительные сведения о: Унсафенклнативемесодс Class'
title: Класс Унсафенклнативемесодс (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.UnsafeNclNativeMethods
- System.Net.UnsafeNclNativeMethods.NativePKI
- System.Net.UnsafeNclNativeMethods.NativePKI.FindClientCertificates
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: fa1084efddae0ba5cbfc9a949dcd94d2c64f3272
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699497"
---
# <a name="unsafenclnativemethods-class"></a>Класс UnsafeNclNativeMethods

Содержит классы, импортирующие ненадежные встроенные сетевые методы. Этот класс не наследуется.

```csharp
internal static class UnsafeNclNativeMethods
```

> [!WARNING]
> Этот класс является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.

## <a name="nativepki-class"></a>Класс Нативепки

Содержит методы, импортированные из crypt32.dll. Эти методы обрабатывали сертификаты при использовании безопасного протокола HTTP (HTTPS). Этот класс не наследуется.

```csharp
internal static class NativePKI
```

## <a name="nativepkifindclientcertificates-method"></a>Нативепки. Финдклиентцертификатес, метод

Обнаружение доступных клиентских сертификатов для отправки на сервер.

```csharp
internal static X509CertificateCollection FindClientCertificates
```

### <a name="return-value"></a>Возвращаемое значение

<xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection?displayProperty=nameWithType>

Коллекция доступных клиентских сертификатов.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Система (в System.dll)
