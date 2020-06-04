---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 0e2051d1b00b881c06082b3af483890d8595899f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400077"
---
# <a name="para-visual-basic"></a>\<para> (Visual Basic)
Указывает, что содержимое форматируется как абзац.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a>Параметры  
 `content`  
 Текст абзаца.  
  
## <a name="remarks"></a>Remarks  
 `<para>`Тег используется внутри тега, например, [\<summary>](summary.md) [\<remarks>](remarks.md) или [\<returns>](returns.md) , и позволяет добавить в текст структуру.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере `<para>` тег используется для разбиения раздела примечаний для `UpdateRecord` метода на два абзаца.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также раздел

- [XML-теги для комментариев](index.md)
