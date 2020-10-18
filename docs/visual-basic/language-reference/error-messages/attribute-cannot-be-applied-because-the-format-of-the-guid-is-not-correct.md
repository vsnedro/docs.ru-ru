---
title: <attribute> не может быть применен из-за неверного формата GUID <number>
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: 8e9ac019470685d9fc45342273096d678a29428d
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162652"
---
# <a name="bc32500-attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>BC32500: " \<attribute> " не может быть применен из \<number> -за неверного формата GUID ""

`COMClassAttribute`Блок атрибутов задает глобальный уникальный идентификатор (GUID), который не соответствует правильному формату GUID. `COMClassAttribute` использует идентификаторы GUID для уникальной идентификации класса, интерфейса и события создания.

 Идентификатор GUID состоит из 16 байтов, первые восемь из которых являются числовыми, а последние восемь — двоичными. Он создается служебными программами Майкрософт, такими как uuidgen.exe и гарантированно уникален в пространстве и времени.

 **Идентификатор ошибки:** BC32500

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Определите правильный идентификатор GUID или GUID, необходимый для определения COM-объекта.

2. Убедитесь в том, что строки GUID, представленные в блоке атрибутов `COMClassAttribute` , скопированы правильно.

## <a name="see-also"></a>См. также

- <xref:System.Guid>
- [Обзор атрибутов](../../programming-guide/concepts/attributes/index.md)
