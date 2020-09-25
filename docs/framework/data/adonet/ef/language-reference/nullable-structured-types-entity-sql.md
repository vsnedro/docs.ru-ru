---
title: Допускающие значения null структурированные типы (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
ms.openlocfilehash: fc2230401ef98c005ab52a845de37482c0dcf698
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202268"
---
# <a name="nullable-structured-types-entity-sql"></a><span data-ttu-id="34e29-102">Допускающие значения null структурированные типы (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="34e29-102">Nullable Structured Types (Entity SQL)</span></span>

<span data-ttu-id="34e29-103">Экземпляр `null` структурированного типа - несуществующий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="34e29-103">A `null` instance of a structured type is an instance that does not exist.</span></span> <span data-ttu-id="34e29-104">Это отличается от существующего экземпляра, все свойства которого имеют значения `null`.</span><span class="sxs-lookup"><span data-stu-id="34e29-104">This is different from an existing instance in which all properties have `null` values.</span></span>  
  
 <span data-ttu-id="34e29-105">В этом разделе описаны структурированные типы, допускающие значение NULL, с указанием, какие типы допускают значение NULL и какие последовательности программного кода формируют экземпляры `null` структурированных типов, допускающих значение NULL.</span><span class="sxs-lookup"><span data-stu-id="34e29-105">This topic describes the nullable structured types, including which types are nullable and which code patterns produce `null` instances of structured nullable types.</span></span>  
  
## <a name="kinds-of-nullable-structured-types"></a><span data-ttu-id="34e29-106">Разновидности структурированных типов, допускающих значение NULL</span><span class="sxs-lookup"><span data-stu-id="34e29-106">Kinds of Nullable Structured Types</span></span>  

 <span data-ttu-id="34e29-107">Существует три вида типов структуры, допускающих значения NULL:</span><span class="sxs-lookup"><span data-stu-id="34e29-107">There are three kinds of nullable structure types:</span></span>  
  
- <span data-ttu-id="34e29-108">Типы строк.</span><span class="sxs-lookup"><span data-stu-id="34e29-108">Row types.</span></span>  
  
- <span data-ttu-id="34e29-109">Сложные типы.</span><span class="sxs-lookup"><span data-stu-id="34e29-109">Complex types.</span></span>  
  
- <span data-ttu-id="34e29-110">Типы сущностей.</span><span class="sxs-lookup"><span data-stu-id="34e29-110">Entity types.</span></span>  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a><span data-ttu-id="34e29-111">Шаблоны кода, которые формируют экземпляры NULL структурированных типов</span><span class="sxs-lookup"><span data-stu-id="34e29-111">Code Patterns that Produce Null Instances of Structured Types</span></span>  

 <span data-ttu-id="34e29-112">В следующем сценарии формируются экземпляры `null`:</span><span class="sxs-lookup"><span data-stu-id="34e29-112">The following scenarios produce `null` instances:</span></span>  
  
- <span data-ttu-id="34e29-113">Формирование `null` как структурированного типа:</span><span class="sxs-lookup"><span data-stu-id="34e29-113">Shaping `null` as a structured type:</span></span>  
  
    ```sql  
    TREAT (NULL AS StructuredType)  
    ```  
  
- <span data-ttu-id="34e29-114">Приведение базового типа к производному типу:</span><span class="sxs-lookup"><span data-stu-id="34e29-114">Upcasting of a base type to a derived type:</span></span>  
  
    ```sql  
    TREAT (BaseType AS DerivedType)  
    ```  
  
- <span data-ttu-id="34e29-115">Внешнее соединение по условию FALSE:</span><span class="sxs-lookup"><span data-stu-id="34e29-115">Outer join on false condition:</span></span>  
  
    ```sql  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="34e29-116">--или</span><span class="sxs-lookup"><span data-stu-id="34e29-116">--or</span></span>  
  
    ```sql  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="34e29-117">--или</span><span class="sxs-lookup"><span data-stu-id="34e29-117">--or</span></span>  
  
    ```sql  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
- <span data-ttu-id="34e29-118">Разыменование ссылки на `null`:</span><span class="sxs-lookup"><span data-stu-id="34e29-118">Dereferencing a `null` reference:</span></span>  
  
    ```sql  
    DEREF(NullRef)  
    ```  
  
- <span data-ttu-id="34e29-119">Получение значения ANYELEMENT из пустой коллекции:</span><span class="sxs-lookup"><span data-stu-id="34e29-119">Obtaining ANYELEMENT from an empty collection:</span></span>  
  
    ```sql  
    ANYELEMENT(EmptyCollection)  
    ```  
  
- <span data-ttu-id="34e29-120">Проверка наличия экземпляров `null` структурированных типов:</span><span class="sxs-lookup"><span data-stu-id="34e29-120">Checking for `null` instances of structured types:</span></span>  
  
    ```csharp  
    ...  
    for (int i = 0; i < reader.FieldCount; i++)  
    {  
        if (reader.IsDBNull(i))  
        {  
            Console.WriteLine("[NULL]");  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="34e29-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="34e29-121">See also</span></span>

- [<span data-ttu-id="34e29-122">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="34e29-122">Entity SQL Overview</span></span>](entity-sql-overview.md)
