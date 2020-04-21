---
title: Копирование и обновление выражений записей
description: Узнайте, как написать "копировать и обновлять выражение", которое копирует существующую запись или анонимные записи, обновляет определенные поля и возвращает обновленную запись или анонимную запись.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: bec3e0ac2fb34e358b199c509c4599b55d7bf35e
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739277"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="aa301-103">Копирование и обновление выражений записей</span><span class="sxs-lookup"><span data-stu-id="aa301-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="aa301-104">*Выражение записи копирования и обновления* — это выражение, которое копирует существующую запись, обновляет определенные поля и возвращает обновленную запись.</span><span class="sxs-lookup"><span data-stu-id="aa301-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="aa301-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa301-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a><span data-ttu-id="aa301-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="aa301-106">Remarks</span></span>

<span data-ttu-id="aa301-107">Записи и анонимные записи неизменяемы по умолчанию, поэтому невозможно обновить существующую запись.</span><span class="sxs-lookup"><span data-stu-id="aa301-107">Records and anonymous records are immutable by default, so it is not possible to update an existing record.</span></span> <span data-ttu-id="aa301-108">Для создания обновленной записи все поля записи должны быть определены еще раз.</span><span class="sxs-lookup"><span data-stu-id="aa301-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="aa301-109">Для упрощения этой задачи можно использовать *выражение копирования и обновления.*</span><span class="sxs-lookup"><span data-stu-id="aa301-109">To simplify this task a *copy and update expression* can be used.</span></span> <span data-ttu-id="aa301-110">Это выражение принимает существующую запись, создает новый тип того же типа, используя определенные поля из выражения и отсутствующее поле, указанное выражением.</span><span class="sxs-lookup"><span data-stu-id="aa301-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>

<span data-ttu-id="aa301-111">Это может быть полезно, когда вам нужно скопировать существующую запись и, возможно, изменить некоторые значения поля.</span><span class="sxs-lookup"><span data-stu-id="aa301-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="aa301-112">Возьмем, к примеру, недавно созданную запись.</span><span class="sxs-lookup"><span data-stu-id="aa301-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="aa301-113">Для обновления только двух полей в этой записи вы можете использовать *выражение записи копии и обновления:*</span><span class="sxs-lookup"><span data-stu-id="aa301-113">To update only two fields in that record you can use the *copy and update record expression*:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="aa301-114">См. также</span><span class="sxs-lookup"><span data-stu-id="aa301-114">See also</span></span>

- [<span data-ttu-id="aa301-115">Записи</span><span class="sxs-lookup"><span data-stu-id="aa301-115">Records</span></span>](records.md)
- [<span data-ttu-id="aa301-116">Анонимные записи</span><span class="sxs-lookup"><span data-stu-id="aa301-116">Anonymous Records</span></span>](anonymous-records.md)
- [<span data-ttu-id="aa301-117">Ссылка на язык F</span><span class="sxs-lookup"><span data-stu-id="aa301-117">F# Language Reference</span></span>](index.md)
