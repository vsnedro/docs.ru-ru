---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 24358a1b004f1cefbfeb3fb8451380ed883841df
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411477"
---
# <a name="value-visual-basic"></a>\<value> (Visual Basic)
Задает описание свойства.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a>Параметры  
 `property-description`  
 Описание свойства.  
  
## <a name="remarks"></a>Комментарии  
 Используйте `<value>` тег для описания свойства. Обратите внимание, что при добавлении свойства с помощью мастера кода в среде разработки Visual Studio будет добавлен [\<summary>](summary.md) тег для нового свойства. Затем следует вручную добавить `<value>` тег для описания значения, которое представляет свойство.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере `<value>` тег используется для описания значения, которое `Counter` содержит свойство.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>См. также раздел

- [XML-теги для комментариев](index.md)
