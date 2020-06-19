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
# <a name="unsafenclnativemethods-class"></a><span data-ttu-id="d7343-102">Класс Унсафенклнативемесодс</span><span class="sxs-lookup"><span data-stu-id="d7343-102">UnsafeNclNativeMethods class</span></span>

<span data-ttu-id="d7343-103">Содержит классы, импортирующие ненадежные встроенные сетевые методы.</span><span class="sxs-lookup"><span data-stu-id="d7343-103">Contains classes that import unsafe native networking methods.</span></span> <span data-ttu-id="d7343-104">Этот класс не может быть унаследован.</span><span class="sxs-lookup"><span data-stu-id="d7343-104">This class cannot be inherited.</span></span>

```csharp
internal static class UnsafeNclNativeMethods
```

> [!WARNING]
> <span data-ttu-id="d7343-105">Этот класс является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="d7343-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="d7343-106">Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="d7343-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="nativepki-class"></a><span data-ttu-id="d7343-107">Класс Нативепки</span><span class="sxs-lookup"><span data-stu-id="d7343-107">NativePKI class</span></span>

<span data-ttu-id="d7343-108">Содержит методы, импортированные из crypt32.dll.</span><span class="sxs-lookup"><span data-stu-id="d7343-108">Contains methods imported from crypt32.dll.</span></span> <span data-ttu-id="d7343-109">Эти методы обрабатывали сертификаты при использовании безопасного протокола HTTP (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="d7343-109">These methods handle certificates when using Hypertext Transfer Protocol Secure (HTTPS).</span></span> <span data-ttu-id="d7343-110">Этот класс не может быть унаследован.</span><span class="sxs-lookup"><span data-stu-id="d7343-110">This class cannot be inherited.</span></span>

```csharp
internal static class NativePKI
```

## <a name="nativepkifindclientcertificates-method"></a><span data-ttu-id="d7343-111">Нативепки. Финдклиентцертификатес, метод</span><span class="sxs-lookup"><span data-stu-id="d7343-111">NativePKI.FindClientCertificates method</span></span>

<span data-ttu-id="d7343-112">Обнаружение доступных клиентских сертификатов для отправки на сервер.</span><span class="sxs-lookup"><span data-stu-id="d7343-112">Discovers available client certificates to send to the server.</span></span>

```csharp
internal static X509CertificateCollection FindClientCertificates
```

### <a name="return-value"></a><span data-ttu-id="d7343-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d7343-113">Return value</span></span>

<xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection?displayProperty=nameWithType>

<span data-ttu-id="d7343-114">Коллекция доступных клиентских сертификатов.</span><span class="sxs-lookup"><span data-stu-id="d7343-114">A collection of available client certificates.</span></span>

## <a name="requirements"></a><span data-ttu-id="d7343-115">Требования</span><span class="sxs-lookup"><span data-stu-id="d7343-115">Requirements</span></span>

<span data-ttu-id="d7343-116">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="d7343-116">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="d7343-117">**Сборка:** Система (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="d7343-117">**Assembly:** System (in System.dll)</span></span>
