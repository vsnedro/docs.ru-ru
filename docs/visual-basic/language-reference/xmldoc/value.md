---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 550f8b63928f80878ba316bfaf09077e14091305
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875179"
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
  
## <a name="remarks"></a>Примечания  

 Используйте `<value>` тег для описания свойства. Обратите внимание, что при добавлении свойства с помощью мастера кода в среде разработки Visual Studio будет добавлен [\<summary>](summary.md) тег для нового свойства. После этого следует вручную добавить тег `<value>` для описания значения, которое представляется свойством.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  

 В этом примере `<value>` тег используется для описания значения, которое `Counter` содержит свойство.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](index.md)
