---
title: <typeparam>
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 0a68cf0a495c2809961e8ec99effa459b0647fec
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866388"
---
# <a name="typeparam-visual-basic"></a>\<typeparam> (Visual Basic)

Определяет имя и описание параметра типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a>Параметры  

 `name`  
 Имя параметра типа. Имя заключается в двойные кавычки (" ").  
  
 `description`  
 Описание параметра типа.  
  
## <a name="remarks"></a>Remarks  

 Используйте `<typeparam>` тег в комментарии для объявления универсального типа или универсального члена, чтобы описать один из параметров типа.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  

 В этом примере `<typeparam>` для описания параметра используется тег `id` .  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](index.md)
