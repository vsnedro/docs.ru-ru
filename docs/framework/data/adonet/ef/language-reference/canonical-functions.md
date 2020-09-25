---
title: Канонические функции
ms.date: 03/30/2017
ms.assetid: bbcc9928-36ea-4dff-9e31-96549ffed958
ms.openlocfilehash: 11e22d527c4266f45ea5d26f2ec95926ebe46332
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185253"
---
# <a name="canonical-functions"></a><span data-ttu-id="cec54-102">Канонические функции</span><span class="sxs-lookup"><span data-stu-id="cec54-102">Canonical Functions</span></span>

<span data-ttu-id="cec54-103">В этом разделе обсуждаются канонические функции, которые поддерживаются всеми поставщиками данных и могут использоваться всеми технологиями запросов.</span><span class="sxs-lookup"><span data-stu-id="cec54-103">This section discusses canonical functions that are supported by all data providers, and can be used by all querying technologies.</span></span> <span data-ttu-id="cec54-104">Канонические функции не могут расширяться поставщиком.</span><span class="sxs-lookup"><span data-stu-id="cec54-104">Canonical functions cannot be extended by a provider.</span></span>  
  
 <span data-ttu-id="cec54-105">Эти канонические функции будут преобразованы в соответствующие функции источника данных для поставщика.</span><span class="sxs-lookup"><span data-stu-id="cec54-105">These canonical functions will be translated to the corresponding data source functionality for the provider.</span></span> <span data-ttu-id="cec54-106">Это позволит формулировать вызовы функций в формате, общем для разных источников данных.</span><span class="sxs-lookup"><span data-stu-id="cec54-106">This allows for function invocations expressed in a common form across data sources.</span></span>  
  
 <span data-ttu-id="cec54-107">Эти канонические функции не зависят от типа источника данных, поэтому для них типы аргументов и возвращаемых значений определяются в терминах типов, доступных в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="cec54-107">Because these canonical functions are independent of data sources, argument and return types of canonical functions are defined in terms of types in the conceptual model.</span></span> <span data-ttu-id="cec54-108">Однако некоторые источники данных поддерживают не все типы в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="cec54-108">However, some data sources might not support all types in the conceptual model.</span></span>  
  
 <span data-ttu-id="cec54-109">При использовании в запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] канонической функции будет вызвана соответствующая функция в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="cec54-109">When canonical functions are used in an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query, the appropriate function will be called at the data source.</span></span>  
  
 <span data-ttu-id="cec54-110">Во всех канонических функциях явным образом определяется обработка входных значений NULL и условия возникновения ошибок.</span><span class="sxs-lookup"><span data-stu-id="cec54-110">All canonical functions have both null-input behavior and error conditions explicitly specified.</span></span> <span data-ttu-id="cec54-111">Поставщики хранилища должны соответствовать этому поведению, но Entity Framework не применяет это поведение.</span><span class="sxs-lookup"><span data-stu-id="cec54-111">Store providers should comply with that behavior, but Entity Framework does not enforce this behavior.</span></span>  
  
 <span data-ttu-id="cec54-112">В сценариях LINQ запросы к Entity Framework содержат сопоставление методов CLR с методами в базовом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="cec54-112">For LINQ scenarios, queries against the Entity Framework involve mapping CLR methods to methods in the underlying data source.</span></span> <span data-ttu-id="cec54-113">Методы CLR сопоставляются с каноническими функциями, и поэтому правильное сопоставление возможно для любого набора методов, независимо от источника данных.</span><span class="sxs-lookup"><span data-stu-id="cec54-113">The CLR methods map to canonical functions, so that a specific set of methods will correctly map, regardless of the data source.</span></span>  
  
## <a name="canonical-functions-namespace"></a><span data-ttu-id="cec54-114">Пространство имен канонических функций</span><span class="sxs-lookup"><span data-stu-id="cec54-114">Canonical Functions Namespace</span></span>  

 <span data-ttu-id="cec54-115">Для канонических функций выделено пространство имен <xref:System.Data.Metadata.Edm>.</span><span class="sxs-lookup"><span data-stu-id="cec54-115">The namespace for canonical function is <xref:System.Data.Metadata.Edm>.</span></span> <span data-ttu-id="cec54-116">Пространство имен <xref:System.Data.Metadata.Edm> автоматически включается во все запросы.</span><span class="sxs-lookup"><span data-stu-id="cec54-116">The <xref:System.Data.Metadata.Edm> namespace is automatically included in all queries.</span></span> <span data-ttu-id="cec54-117">Однако при импорте другого пространства имен, в котором содержится функция с именем, совпадающим с именем канонической функции (из пространства имен <xref:System.Data.Metadata.Edm>), то пространство имен необходимо указывать явным образом.</span><span class="sxs-lookup"><span data-stu-id="cec54-117">However, if another namespace is imported that contains a function with the same name as a canonical function (in the <xref:System.Data.Metadata.Edm> namespace), you must specify the namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cec54-118">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="cec54-118">In This Section</span></span>  

 [<span data-ttu-id="cec54-119">Статистические канонические функции</span><span class="sxs-lookup"><span data-stu-id="cec54-119">Aggregate Canonical Functions</span></span>](aggregate-canonical-functions.md)  
 <span data-ttu-id="cec54-120">Обсуждаются статистические канонические функции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cec54-120">Discusses aggregate [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="cec54-121">Математические канонические функции</span><span class="sxs-lookup"><span data-stu-id="cec54-121">Math Canonical Functions</span></span>](math-canonical-functions.md)  
 <span data-ttu-id="cec54-122">Обсуждаются математические канонические функции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cec54-122">Discusses math [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="cec54-123">Строковые канонические функции</span><span class="sxs-lookup"><span data-stu-id="cec54-123">String Canonical Functions</span></span>](string-canonical-functions.md)  
 <span data-ttu-id="cec54-124">Обсуждаются строковые канонические функции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cec54-124">Discusses string [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="cec54-125">Канонические функции даты и времени</span><span class="sxs-lookup"><span data-stu-id="cec54-125">Date and Time Canonical Functions</span></span>](date-and-time-canonical-functions.md)  
 <span data-ttu-id="cec54-126">Обсуждаются канонические функции даты и времени в языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cec54-126">Discusses date and time [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="cec54-127">Битовые канонические функции</span><span class="sxs-lookup"><span data-stu-id="cec54-127">Bitwise Canonical Functions</span></span>](bitwise-canonical-functions.md)  
 <span data-ttu-id="cec54-128">Обсуждаются побитовые канонические функции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cec54-128">Discusses bitwise [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="cec54-129">Пространственные функции</span><span class="sxs-lookup"><span data-stu-id="cec54-129">Spatial Functions</span></span>](spatial-functions.md)  
 <span data-ttu-id="cec54-130">Рассматриваются пространственные канонические функции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cec54-130">Discusses Spatial [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="cec54-131">Прочие канонические функции</span><span class="sxs-lookup"><span data-stu-id="cec54-131">Other Canonical Functions</span></span>](other-canonical-functions.md)  
 <span data-ttu-id="cec54-132">Обсуждаются функции, которые не являются побитовыми, строковыми, математическими, статистическими или функциями даты-времени.</span><span class="sxs-lookup"><span data-stu-id="cec54-132">Discusses functions not classified as bitwise, date/time, string, math, or aggregate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cec54-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cec54-133">See also</span></span>

- [<span data-ttu-id="cec54-134">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="cec54-134">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="cec54-135">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="cec54-135">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="cec54-136">Сопоставление канонических функций концептуальной модели с функциями SQL Server</span><span class="sxs-lookup"><span data-stu-id="cec54-136">Conceptual Model Canonical to SQL Server Functions Mapping</span></span>](../conceptual-model-canonical-to-sql-server-functions-mapping.md)
- [<span data-ttu-id="cec54-137">Определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="cec54-137">User-Defined Functions</span></span>](user-defined-functions-entity-sql.md)
