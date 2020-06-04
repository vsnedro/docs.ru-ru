---
title: <attribute> не может быть применен из-за неверного формата GUID <number>
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: 554c38c8f44999feba4cfa04d58ce2f07e955eb1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409924"
---
# <a name="attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>\<attribute> не может быть применен из-за неверного формата GUID \<number>

`COMClassAttribute`Блок атрибутов задает глобальный уникальный идентификатор (GUID), который не соответствует правильному формату GUID. `COMClassAttribute`использует идентификаторы GUID для уникальной идентификации класса, интерфейса и события создания.  
  
 Идентификатор GUID состоит из 16 байтов, первые восемь из которых являются числовыми, а последние восемь — двоичными. Она создается служебными программами Майкрософт, такими как uuidgen. exe, и гарантируется уникальность в пространстве и времени.  
  
 **Идентификатор ошибки:** BC32500  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Определите правильный идентификатор GUID или GUID, необходимый для определения COM-объекта.  
  
2. Убедитесь в том, что строки GUID, представленные в блоке атрибутов `COMClassAttribute` , скопированы правильно.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Guid>
- [Обзор атрибутов](../../programming-guide/concepts/attributes/index.md)
