---
title: Класс Маиладдресспарсер (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.MailAddressParser
- System.Net.Mail.MailAddressParser.ParseAddress
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ff83f6946539fa262ccde980052627f98c75601d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051354"
---
# <a name="mailaddressparser-class"></a><span data-ttu-id="fc717-102">Класс MailAddressParser</span><span class="sxs-lookup"><span data-stu-id="fc717-102">MailAddressParser class</span></span>

<span data-ttu-id="fc717-103">Анализирует адреса электронной почты, как описано в RFC 2822.</span><span class="sxs-lookup"><span data-stu-id="fc717-103">Parses email addresses as described in RFC 2822.</span></span> <span data-ttu-id="fc717-104">Этот класс не может быть унаследован.</span><span class="sxs-lookup"><span data-stu-id="fc717-104">This class cannot be inherited.</span></span>

```csharp
internal static class MailAddressParser
```

> [!WARNING]
> <span data-ttu-id="fc717-105">Этот класс является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="fc717-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="fc717-106">Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="fc717-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="parseaddress-method"></a><span data-ttu-id="fc717-107">Метод Парсеаддресс</span><span class="sxs-lookup"><span data-stu-id="fc717-107">ParseAddress method</span></span>

<span data-ttu-id="fc717-108">Выполняет синтаксический анализ одного адреса электронной почты из указанной строки.</span><span class="sxs-lookup"><span data-stu-id="fc717-108">Parses a single email address from the specified string.</span></span>

```csharp
internal static MailAddress ParseAddress(string data)
```

### <a name="parameters"></a><span data-ttu-id="fc717-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc717-109">Parameters</span></span>

<span data-ttu-id="fc717-110">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="fc717-110">`data` <xref:System.String></span></span>

<span data-ttu-id="fc717-111">Строка, содержащая адрес электронной почты для синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="fc717-111">The string that contains an email address to be parsed.</span></span>

### <a name="return-value"></a><span data-ttu-id="fc717-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fc717-112">Return value</span></span>

<xref:System.Net.Mail.MailAddress>

<span data-ttu-id="fc717-113">Допустимый адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="fc717-113">A valid email address.</span></span>

### <a name="exceptions"></a><span data-ttu-id="fc717-114">Исключения</span><span class="sxs-lookup"><span data-stu-id="fc717-114">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="fc717-115">Недопустимый адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="fc717-115">The email address is invalid.</span></span>

## <a name="requirements"></a><span data-ttu-id="fc717-116">Требования</span><span class="sxs-lookup"><span data-stu-id="fc717-116">Requirements</span></span>

<span data-ttu-id="fc717-117">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="fc717-117">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="fc717-118">**Сборка:** Система (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="fc717-118">**Assembly:** System (in System.dll)</span></span>
