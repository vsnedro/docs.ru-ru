---
title: Класс Куотедпаирреадер (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.QuotedPairReader
- System.Net.Mail.QuotedPairReader.CountQuotedChars
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 898c6e9d2d5dd02f3d5f9c096ad470b5dd445d1d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051315"
---
# <a name="quotedpairreader-class"></a><span data-ttu-id="017e0-102">Класс QuotedPairReader</span><span class="sxs-lookup"><span data-stu-id="017e0-102">QuotedPairReader class</span></span>

<span data-ttu-id="017e0-103">Определяет, какие символы в строке заключены в кавычки (экранированные).</span><span class="sxs-lookup"><span data-stu-id="017e0-103">Determines which characters are quoted (escaped) in a quoted string.</span></span> <span data-ttu-id="017e0-104">Этот класс не может быть унаследован.</span><span class="sxs-lookup"><span data-stu-id="017e0-104">This class cannot be inherited.</span></span>

```csharp
internal static class QuotedPairReader
```

> [!WARNING]
> <span data-ttu-id="017e0-105">Этот класс является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="017e0-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="017e0-106">Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="017e0-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="countquotedchars-method"></a><span data-ttu-id="017e0-107">Метод Каунткуотедчарс</span><span class="sxs-lookup"><span data-stu-id="017e0-107">CountQuotedChars method</span></span>

<span data-ttu-id="017e0-108">Подсчитывает количество последовательных заключенных в кавычки символов, включая несколько предшествующих кавычек, в указанной строке.</span><span class="sxs-lookup"><span data-stu-id="017e0-108">Counts the number of consecutive quoted characters, including multiple preceding quoted backslashes, in the specified string.</span></span> <span data-ttu-id="017e0-109">Например, если задана строка `a\\\b` и индекс `4` , метод возвращает значение `4` , так как `b` заключено в кавычки и поэтому являются три предшествующих обратной косой черты.</span><span class="sxs-lookup"><span data-stu-id="017e0-109">For example, given the string `a\\\b` and an index of `4`, the method returns `4`, because `b` is quoted and so are the three preceding backslashes.</span></span>

```csharp
internal static int CountQuotedChars(string data, int index, bool permitUnicodeEscaping)
```

### <a name="parameters"></a><span data-ttu-id="017e0-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="017e0-110">Parameters</span></span>

- <span data-ttu-id="017e0-111">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="017e0-111">`data` <xref:System.String></span></span>

  <span data-ttu-id="017e0-112">Строка данных, в которой подсчитывается число последовательных символов в кавычках.</span><span class="sxs-lookup"><span data-stu-id="017e0-112">The data string in which to count consecutive quoted characters.</span></span>

- <span data-ttu-id="017e0-113">`index` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="017e0-113">`index` <xref:System.Int32></span></span>

  <span data-ttu-id="017e0-114">Строка в указанной строке до и включает в себя подсчет последовательных символов в кавычках.</span><span class="sxs-lookup"><span data-stu-id="017e0-114">The position in the specified string up to and including which consecutive quoted characters should be counted.</span></span>

- <span data-ttu-id="017e0-115">`permitUnicodeEscaping` <xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="017e0-115">`permitUnicodeEscaping` <xref:System.Boolean></span></span>

  <span data-ttu-id="017e0-116">`true`значение для запрета экранирования символов Юникода; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="017e0-116">`true` to permit Unicode characters to be escaped; otherwise, `false`.</span></span>

### <a name="return-value"></a><span data-ttu-id="017e0-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="017e0-117">Return value</span></span>

<xref:System.Int32?displayProperty=nameWithType>

<span data-ttu-id="017e0-118">`0`значение, если символ по указанному индексу не экранирован; в противном случае — число последовательных символов в кавычках до символа, включая символ `index` .</span><span class="sxs-lookup"><span data-stu-id="017e0-118">`0` if the character at the specified index is not escaped; otherwise, the number of consecutive quoted characters up to and including the character at `index`.</span></span>

### <a name="exceptions"></a><span data-ttu-id="017e0-119">Исключения</span><span class="sxs-lookup"><span data-stu-id="017e0-119">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="017e0-120">Escape-символ Юникода найден, но не разрешен.</span><span class="sxs-lookup"><span data-stu-id="017e0-120">An escaped Unicode character was found but is not permitted.</span></span>

## <a name="requirements"></a><span data-ttu-id="017e0-121">Требования</span><span class="sxs-lookup"><span data-stu-id="017e0-121">Requirements</span></span>

<span data-ttu-id="017e0-122">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="017e0-122">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="017e0-123">**Сборка:** Система (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="017e0-123">**Assembly:** System (in System.dll)</span></span>
