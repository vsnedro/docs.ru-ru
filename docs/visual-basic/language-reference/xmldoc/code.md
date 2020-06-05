---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: aa65fed863718f1f00b510f82051a13e764e1b23
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400152"
---
# <a name="code-visual-basic"></a>\<code> (Visual Basic)
Указывает, что текст представляет собой несколько строк кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a>Параметры  
 `content`  
 Текст, помечающий как код.  
  
## <a name="remarks"></a>Комментарии  
 Используйте `<code>` тег, чтобы указать несколько строк в виде кода. Используйте, [\<c>](c.md) чтобы указать, что текст в описании должен быть помечен как код.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере \<code> тег используется для включения примера кода для использования `ID` поля.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>См. также раздел

- [XML-теги для комментариев](index.md)
