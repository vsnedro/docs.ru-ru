---
title: Строки соединения
description: Сведения о строках подключения в ADO.NET, которые содержат сведения об инициализации, передаваемые в качестве параметра из поставщика данных в источник данных.
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: baa6599a532746895cbb3920f2c623dd4c2be864
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287029"
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="610a8-103">Строки подключения в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="610a8-103">Connection Strings in ADO.NET</span></span>

<span data-ttu-id="610a8-104">Строка подключения содержит сведения для инициализации, передаваемые в виде параметра от поставщика данных в источник данных.</span><span class="sxs-lookup"><span data-stu-id="610a8-104">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="610a8-105">Поставщик данных получает строку подключения в качестве значения <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> Свойства.</span><span class="sxs-lookup"><span data-stu-id="610a8-105">The data provider receives the connection string as the value of the <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="610a8-106">Поставщик анализирует строку подключения и проверяет правильность синтаксиса и наличие ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="610a8-106">The provider parses the connection string and ensures that the syntax is correct and that the keywords are supported.</span></span> <span data-ttu-id="610a8-107">Затем <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> метод передает проанализированные параметры соединения в источник данных.</span><span class="sxs-lookup"><span data-stu-id="610a8-107">Then the <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> method passes the parsed connection parameters to the data source.</span></span> <span data-ttu-id="610a8-108">Источник данных выполняет дальнейшую проверку и устанавливает соединение.</span><span class="sxs-lookup"><span data-stu-id="610a8-108">The data source performs further validation and establishes a connection.</span></span>

## <a name="connection-string-syntax"></a><span data-ttu-id="610a8-109">Синтаксис строки подключения</span><span class="sxs-lookup"><span data-stu-id="610a8-109">Connection string syntax</span></span>

<span data-ttu-id="610a8-110">Строка подключения представляет собой разделенный точками с запятой список пар параметров "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="610a8-110">A connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>

```csharp
keyword1=value; keyword2=value;
```

<span data-ttu-id="610a8-111">Ключевые слова не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="610a8-111">Keywords are not case-sensitive.</span></span> <span data-ttu-id="610a8-112">При этом значения в зависимости от источника данных могут быть чувствительны к регистру.</span><span class="sxs-lookup"><span data-stu-id="610a8-112">Values, however, may be case-sensitive, depending on the data source.</span></span> <span data-ttu-id="610a8-113">Ключевые слова и значения могут содержать [символы пробела](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span><span class="sxs-lookup"><span data-stu-id="610a8-113">Both keywords and values may contain [whitespace characters](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span></span> <span data-ttu-id="610a8-114">Начальные и конечные пробелы игнорируются в ключевых словах и в значениях, не заключенных в кавычки.</span><span class="sxs-lookup"><span data-stu-id="610a8-114">Leading and trailing white space is ignored in keywords and unquoted values.</span></span>

<span data-ttu-id="610a8-115">Если значение содержит точку с запятой, [управляющие символы Юникода](https://en.wikipedia.org/wiki/Unicode_control_characters)или начальные или конечные пробелы, их необходимо заключить в одинарные или двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="610a8-115">If a value contains the semicolon, [Unicode control characters](https://en.wikipedia.org/wiki/Unicode_control_characters), or leading or trailing white space, it must be enclosed in single or double quotation marks.</span></span> <span data-ttu-id="610a8-116">Например:</span><span class="sxs-lookup"><span data-stu-id="610a8-116">For example:</span></span>

```csharp
Keyword=" whitespace  ";
Keyword='special;character';
```

<span data-ttu-id="610a8-117">Окружающий символ может не находиться в заключенном в нем значении.</span><span class="sxs-lookup"><span data-stu-id="610a8-117">The enclosing character may not occur within the value it encloses.</span></span> <span data-ttu-id="610a8-118">Таким образом, значение, содержащее одинарные кавычки, может быть заключено только в двойные кавычки и наоборот:</span><span class="sxs-lookup"><span data-stu-id="610a8-118">Therefore, a value containing single quotation marks can be enclosed only in double quotation marks, and vice versa:</span></span>

```csharp
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

<span data-ttu-id="610a8-119">Можно также поэкранировать окружающий символ, используя два из них:</span><span class="sxs-lookup"><span data-stu-id="610a8-119">You can also escape the enclosing character by using two of them together:</span></span>

```csharp
Keyword="double""quotation";
Keyword='single''quotation';
```

<span data-ttu-id="610a8-120">Кавычки, а также знак равенства не требуются для экранирования, поэтому следующие строки соединения являются допустимыми:</span><span class="sxs-lookup"><span data-stu-id="610a8-120">The quotation marks themselves, as well as the equals sign, do not require escaping, so the following connection strings are valid:</span></span>

```csharp
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

<span data-ttu-id="610a8-121">Так как каждое значение считывается до следующей точки с запятой или конца строки, значение в последнем примере равно `a=b=c` , а конечная точка с запятой является необязательной.</span><span class="sxs-lookup"><span data-stu-id="610a8-121">Since each value is read till the next semicolon or the end of string, the value in the latter example is `a=b=c`, and the final semicolon is optional.</span></span>

<span data-ttu-id="610a8-122">Все строки подключения имеют один и тот же базовый синтаксис, описанный выше.</span><span class="sxs-lookup"><span data-stu-id="610a8-122">All connection strings share the same basic syntax described above.</span></span> <span data-ttu-id="610a8-123">Набор распознаваемых ключевых слов зависит от поставщика, но в течение многих лет он превратился в предыдущие API-интерфейсы, такие как *ODBC*.</span><span class="sxs-lookup"><span data-stu-id="610a8-123">The set of recognized keywords depends on the provider, however, and has evolved over the years from earlier APIs such as *ODBC*.</span></span> <span data-ttu-id="610a8-124">Поставщик данных *.NET Framework* для *SQL Server* ( `SqlClient` ) поддерживает много ключевых слов из старых API-интерфейсов, но обычно является более гибким и принимает синонимы для многих общих ключевых слов строки подключения.</span><span class="sxs-lookup"><span data-stu-id="610a8-124">The *.NET Framework* data provider for *SQL Server* (`SqlClient`) supports many keywords from older APIs, but is generally more flexible and accepts synonyms for many of the common connection string keywords.</span></span>

<span data-ttu-id="610a8-125">При вводе ошибок могут возникать ошибки.</span><span class="sxs-lookup"><span data-stu-id="610a8-125">Typing mistakes can cause errors.</span></span> <span data-ttu-id="610a8-126">Например, `Integrated Security=true` является допустимым, но `IntegratedSecurity=true` вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="610a8-126">For example, `Integrated Security=true` is valid, but `IntegratedSecurity=true` causes an error.</span></span>

<span data-ttu-id="610a8-127">Строки подключения, созданные вручную во время выполнения из непроверенных входных данных, уязвимы для атак путем внедрения строк и поддают риску безопасность в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="610a8-127">Connection strings constructed manually at run time from unvalidated user input are vulnerable to string-injection attacks and jeopardize security at the data source.</span></span> <span data-ttu-id="610a8-128">Для решения этих проблем в *ADO.NET* 2,0 появились [построители строк подключения](connection-string-builders.md) для каждого *.NET Framework* поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="610a8-128">To address these problems, *ADO.NET* 2.0 introduced [connection string builders](connection-string-builders.md) for each *.NET Framework* data provider.</span></span> <span data-ttu-id="610a8-129">Эти построители строк подключения предоставляют параметры в виде строго типизированных свойств и позволяют проверить строку подключения перед отправкой в источник данных.</span><span class="sxs-lookup"><span data-stu-id="610a8-129">These connection string builders expose parameters as strongly typed properties, and make it possible to validate the connection string before it's sent to the data source.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="610a8-130">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="610a8-130">In This Section</span></span>

<span data-ttu-id="610a8-131">[Построители строк подключения](connection-string-builders.md)</span><span class="sxs-lookup"><span data-stu-id="610a8-131">[Connection String Builders](connection-string-builders.md)</span></span>\
<span data-ttu-id="610a8-132">Демонстрирует использование классов `ConnectionStringBuilder` для создания достоверных строк соединения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="610a8-132">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>

<span data-ttu-id="610a8-133">[Строки подключения и файлы конфигурации](connection-strings-and-configuration-files.md)</span><span class="sxs-lookup"><span data-stu-id="610a8-133">[Connection Strings and Configuration Files](connection-strings-and-configuration-files.md)</span></span>\
<span data-ttu-id="610a8-134">Демонстрирует хранение и получение строк соединения в файлах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="610a8-134">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>

<span data-ttu-id="610a8-135">[Синтаксис строки подключения](connection-string-syntax.md)</span><span class="sxs-lookup"><span data-stu-id="610a8-135">[Connection String Syntax](connection-string-syntax.md)</span></span>\
<span data-ttu-id="610a8-136">Описывает настройку строк соединения, зависящих от поставщика, для `SqlClient`, `OracleClient`, `OleDb` и `Odbc`.</span><span class="sxs-lookup"><span data-stu-id="610a8-136">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>

<span data-ttu-id="610a8-137">[Защита сведений о соединении](protecting-connection-information.md)</span><span class="sxs-lookup"><span data-stu-id="610a8-137">[Protecting Connection Information](protecting-connection-information.md)</span></span>\
<span data-ttu-id="610a8-138">Демонстрирует методы защиты сведений, используемых для подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="610a8-138">Demonstrates techniques for protecting information used to connect to a data source.</span></span>

## <a name="see-also"></a><span data-ttu-id="610a8-139">См. также</span><span class="sxs-lookup"><span data-stu-id="610a8-139">See also</span></span>

- [<span data-ttu-id="610a8-140">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="610a8-140">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)
- [<span data-ttu-id="610a8-141">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="610a8-141">ADO.NET Overview</span></span>](ado-net-overview.md)
