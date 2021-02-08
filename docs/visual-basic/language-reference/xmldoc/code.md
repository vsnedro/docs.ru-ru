---
description: 'Дополнительные сведения: <code>(Visual Basic)'
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: 80fc0988f60d9d82b9c88734f86b20ebccc80b7c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787504"
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
  
## <a name="remarks"></a>Remarks  

 Используйте `<code>` тег, чтобы указать несколько строк в виде кода. Используйте, [\<c>](c.md) чтобы указать, что текст в описании должен быть помечен как код.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  

 В этом примере \<code> тег используется для включения примера кода для использования `ID` поля.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](index.md)
