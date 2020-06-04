---
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 42f40581d252956433165789d6674234a295867c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400151"
---
# <a name="example-visual-basic"></a>\<example> (Visual Basic)
Указывает пример для элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a>Параметры  
 `description`  
 Описание примера кода.  
  
## <a name="remarks"></a>Remarks  
 `<example>`Тег позволяет указать пример использования метода или другого элемента библиотеки. Обычно это касается использования [\<code>](code.md) тега.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере `<example>` тег используется для включения примера использования `ID` поля.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>См. также раздел

- [XML-теги для комментариев](index.md)
