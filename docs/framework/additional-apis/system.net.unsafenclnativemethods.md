---
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
ms.openlocfilehash: 46756a0d1d69b4768dbb8dcdd7ab098d3f1849bf
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990464"
---
# <a name="unsafenclnativemethods-class"></a>Класс Унсафенклнативемесодс

Содержит классы, импортирующие ненадежные встроенные сетевые методы. Этот класс не может быть унаследован.

```csharp
internal static class UnsafeNclNativeMethods
```

> [!WARNING]
> Этот класс является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.

## <a name="nativepki-class"></a>Класс Нативепки

Содержит методы, импортированные из crypt32.dll. Эти методы обрабатывали сертификаты при использовании безопасного протокола HTTP (HTTPS). Этот класс не может быть унаследован.

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
