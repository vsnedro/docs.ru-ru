---
title: Класс Куотедпаирреадер (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.QuotedPairReader
- System.Net.QuotedPairReader.CountQuotedChars
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 9b0bf835a34eecc651894f4336648b73a81b665c
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990502"
---
# <a name="quotedpairreader-class"></a><span data-ttu-id="ebf68-102">Класс Куотедпаирреадер</span><span class="sxs-lookup"><span data-stu-id="ebf68-102">QuotedPairReader class</span></span>

<span data-ttu-id="ebf68-103">Определяет, какие символы в строке заключены в кавычки (экранированные).</span><span class="sxs-lookup"><span data-stu-id="ebf68-103">Determines which characters are quoted (escaped) in a quoted string.</span></span> <span data-ttu-id="ebf68-104">Этот класс не может быть унаследован.</span><span class="sxs-lookup"><span data-stu-id="ebf68-104">This class cannot be inherited.</span></span>

```csharp
internal static class QuotedPairReader
```

> [!WARNING]
> <span data-ttu-id="ebf68-105">Этот класс является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="ebf68-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="ebf68-106">Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="ebf68-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="countquotedchars-method"></a><span data-ttu-id="ebf68-107">Метод Каунткуотедчарс</span><span class="sxs-lookup"><span data-stu-id="ebf68-107">CountQuotedChars method</span></span>

<span data-ttu-id="ebf68-108">Подсчитывает количество последовательных заключенных в кавычки символов, включая несколько предшествующих кавычек, в указанной строке.</span><span class="sxs-lookup"><span data-stu-id="ebf68-108">Counts the number of consecutive quoted characters, including multiple preceding quoted backslashes, in the specified string.</span></span> <span data-ttu-id="ebf68-109">Например, если задана строка `a\\\b` и индекс `4` , метод возвращает значение `4` , так как `b` заключено в кавычки и поэтому являются три предшествующих обратной косой черты.</span><span class="sxs-lookup"><span data-stu-id="ebf68-109">For example, given the string `a\\\b` and an index of `4`, the method returns `4`, because `b` is quoted and so are the three preceding backslashes.</span></span>

```csharp
internal static int CountQuotedChars(string data, int index, bool permitUnicodeEscaping)
```

### <a name="parameters"></a><span data-ttu-id="ebf68-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="ebf68-110">Parameters</span></span>

- <span data-ttu-id="ebf68-111">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ebf68-111">`data` <xref:System.String></span></span>

  <span data-ttu-id="ebf68-112">Строка данных, в которой подсчитывается число последовательных символов в кавычках.</span><span class="sxs-lookup"><span data-stu-id="ebf68-112">The data string in which to count consecutive quoted characters.</span></span>

- <span data-ttu-id="ebf68-113">`index` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="ebf68-113">`index` <xref:System.Int32></span></span>

  <span data-ttu-id="ebf68-114">Строка в указанной строке до и включает в себя подсчет последовательных символов в кавычках.</span><span class="sxs-lookup"><span data-stu-id="ebf68-114">The position in the specified string up to and including which consecutive quoted characters should be counted.</span></span>

- <span data-ttu-id="ebf68-115">`permitUnicodeEscaping` <xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="ebf68-115">`permitUnicodeEscaping` <xref:System.Boolean></span></span>

  <span data-ttu-id="ebf68-116">`true`значение для запрета экранирования символов Юникода; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="ebf68-116">`true` to permit Unicode characters to be escaped; otherwise, `false`.</span></span>

### <a name="return-value"></a><span data-ttu-id="ebf68-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ebf68-117">Return value</span></span>

<xref:System.Int32?displayProperty=nameWithType>

<span data-ttu-id="ebf68-118">`0`значение, если символ по указанному индексу не экранирован; в противном случае — число последовательных символов в кавычках до символа, включая символ `index` .</span><span class="sxs-lookup"><span data-stu-id="ebf68-118">`0` if the character at the specified index is not escaped; otherwise, the number of consecutive quoted characters up to and including the character at `index`.</span></span>

### <a name="exceptions"></a><span data-ttu-id="ebf68-119">Исключения</span><span class="sxs-lookup"><span data-stu-id="ebf68-119">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="ebf68-120">Escape-символ Юникода найден, но не разрешен.</span><span class="sxs-lookup"><span data-stu-id="ebf68-120">An escaped Unicode character was found but is not permitted.</span></span>

## <a name="requirements"></a><span data-ttu-id="ebf68-121">Требования</span><span class="sxs-lookup"><span data-stu-id="ebf68-121">Requirements</span></span>

<span data-ttu-id="ebf68-122">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="ebf68-122">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="ebf68-123">**Сборка:** Система (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="ebf68-123">**Assembly:** System (in System.dll)</span></span>
