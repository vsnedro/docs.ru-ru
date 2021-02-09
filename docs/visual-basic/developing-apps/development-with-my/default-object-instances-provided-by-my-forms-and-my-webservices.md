---
description: 'Узнайте подробнее о: Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию (Visual Basic)'
title: Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 34363a56577ca0fafb839e782a8066bd8a8c5a14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99775361"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию (Visual Basic)

Объекты [My.Forms](../../language-reference/objects/my-forms-object.md) и [My.WebServices](../../language-reference/objects/my-webservices-object.md) предоставляют доступ к формам, источникам данных и веб-службам XML, используемым вашим приложением. Для этого они используют коллекции *экземпляров по умолчанию* каждого из этих объектов.  
  
## <a name="default-instances"></a>Экземпляры по умолчанию  

 Экземпляр по умолчанию — это экземпляр класса, который предоставляется средой выполнения и не требует объявления и создания экземпляра с помощью инструкций `Dim` и `New`. В следующем примере показано, как раньше можно было объявить и создать экземпляр класса <xref:System.Windows.Forms.Form> с именем `Form1` и как теперь можно получить экземпляр по умолчанию этого класса <xref:System.Windows.Forms.Form> через `My.Forms`.  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 Объект `My.Forms` возвращает коллекцию экземпляров по умолчанию для каждого класса `Form`, существующего в проекте. Аналогичным образом, `My.WebServices` предоставляет экземпляр прокси-класса по умолчанию для каждой веб-службы, на которую вы ссылались в приложении.  
  
## <a name="see-also"></a>См. также

- [Объект My.Forms](../../language-reference/objects/my-forms-object.md)
- [Объект My.WebServices](../../language-reference/objects/my-webservices-object.md)
- [Зависимость My от типа проекта](how-my-depends-on-project-type.md)
