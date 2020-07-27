---
title: Практическое руководство. Реализация свойства зависимостей
description: Определите свойство зависимостей в Windows Presentation Foundation, создав резервную копию свойства среды CLR с полем DependencyProperty.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: 673f653a9b02627efcccdfe08c4812ca0834217c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165100"
---
# <a name="how-to-implement-a-dependency-property"></a>Практическое руководство. Реализация свойства зависимостей
В этом примере показано, как выполнить обратное создание свойства среды CLR с <xref:System.Windows.DependencyProperty> полем, определив таким образом свойство зависимостей. Если вы определяете собственные свойства и хотите, чтобы они поддерживали множество аспектов функциональности [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], включая стили, привязку данных, наследование, анимацию и значения по умолчанию, следует реализовать их как свойства зависимостей.  
  
## <a name="example"></a>Пример  
 В следующем примере сначала регистрируется свойство зависимости путем вызова <xref:System.Windows.DependencyProperty.Register%2A> метода. Имя поля идентификатора, используемого для хранения имени и характеристик свойства зависимостей, должно быть <xref:System.Windows.DependencyProperty.Name%2A> выбрано для свойства зависимостей в рамках <xref:System.Windows.DependencyProperty.Register%2A> вызова, к которому добавляется строка литерала `Property` . Например, если зарегистрировать свойство зависимостей с помощью <xref:System.Windows.DependencyProperty.Name%2A> объекта `Location` , то поле идентификатора, определяемое для свойства зависимостей, должно иметь имя `LocationProperty` .  
  
 В этом примере имя свойства зависимостей и его метод доступа CLR имеет значение; `State` поле идентификатора имеет значение `StateProperty` ; тип свойства —, <xref:System.Boolean> а тип, регистрирующий свойство зависимостей, — `MyStateControl` .  
  
 Если не следовать этому шаблону именования, конструкторы могут неправильно обработать свойство и определенные аспекты применения стиля в системе свойств могут работать не так, как ожидалось.  
  
 Для свойства зависимости можно также указать используемые по умолчанию метаданные. В этом примере в качестве значения по умолчанию для свойства зависимости `State` регистрируется значение `false`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 Дополнительные сведения о том, как и Зачем реализовывать свойство зависимостей, в отличие от простого резервного копирования свойства CLR с закрытым полем, см. в разделе [Общие сведения о свойствах зависимостей](dependency-properties-overview.md).  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения о свойствах зависимости](dependency-properties-overview.md)
- [Практические руководства](properties-how-to-topics.md)
