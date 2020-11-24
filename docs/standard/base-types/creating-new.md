---
title: Создание новых строк в .NET
description: Сведения о создании строк с помощью присваивания, конструкторов классов или методов System.String, объединяющих несколько строк, массивов строк или объектов в .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CopyTo method
- Join method
- Format method
- Concat method
- strings [.NET], creating
- Insert method
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
ms.openlocfilehash: a00274b7b6b7e7a54d8546f2176109688a4c4678
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824887"
---
# <a name="creating-new-strings-in-net"></a>Создание новых строк в .NET

. NET позволяет создавать строки с помощью простой операции присваивания, а также перегружать конструктор класса для создания строк с помощью нескольких различных параметров. Кроме того, .NET предоставляет в классе <xref:System.String?displayProperty=nameWithType> несколько методов для создания строковых объектов путем объединения строк, массивов строк или объектов.  
  
## <a name="creating-strings-using-assignment"></a>Создание строк с помощью присваивания  
 Самый простой способ создать объект <xref:System.String> — присвоить строковый литерал объекту <xref:System.String>.  
  
## <a name="creating-strings-using-a-class-constructor"></a>Создание строк с помощью конструктора класса  
 С помощью перегруженного конструктора класса <xref:System.String> можно создавать строки из массивов символов. Кроме того, строки можно создавать путем копирования того или иного знака указанное количество раз.  
  
## <a name="methods-that-return-strings"></a>Методы, возвращающие строки  
 В следующей таблице перечислено несколько полезных методов, которые возвращают строковые объекты.  
  
|Имя метода|Использовать|  
|-----------------|---------|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|Создание форматированной строки из набора объектов ввода.|  
|<xref:System.String.Concat%2A?displayProperty=nameWithType>|Создание строк из двух или более строк.|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|Создание новой строки с помощью объединения массива строк.|  
|<xref:System.String.Insert%2A?displayProperty=nameWithType>|Создание новой строки с помощью вставки строки в указанную позицию существующей строки.|  
|<xref:System.String.CopyTo%2A?displayProperty=nameWithType>|Копирование указанных знаков в строке в указанную позицию в массиве символов.|  
  
### <a name="format"></a>Формат  
 Метод **String.Format** позволяет создавать форматированные строки и сцеплять строки, представляющие несколько объектов. Этот метод автоматически преобразует в строку любой переданный объект. Например, если приложение должно предоставить пользователю значение **Int32** и значение **DateTime**, с помощью метода **Format** вы можете соединить их в одну строку для отображения. Сведения о правилах форматирования, используемых в этом методе, см. в разделе [Составное форматирование](composite-formatting.md).  
  
 В следующем примере метод **Format** используется для создания строки, содержащей целочисленную переменную.  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 В этом примере <xref:System.DateTime.Now%2A?displayProperty=nameWithType> выводит текущую дату и время с учетом языка и региональных параметров, связанных с текущим потоком.  
  
### <a name="concat"></a>Concat  
 Метод **String.Concat** позволяет легко создать новый строковый объект из двух или более существующих объектов. Он позволяет использовать независимый от языка способ сцепления строк. Этот метод принимает любой класс, производный от **System.Object**. В следующем примере создается строка из двух существующих объектов строки и символа разделителя.  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### <a name="join"></a>Join  
 Метод **String.Join** создает строку из массива строк и разделительной строки. Этот метод полезен в случае необходимости сцепления нескольких строк и создания списка, отделенного, например, запятой.  
  
 В следующем примере используется пробел для привязки массива строк.  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### <a name="insert"></a>Insert  
 Метод **String.Insert** создает новую строку, вставляя предоставленную строку в указанную позицию в другой строке. Этот метод использует отсчитываемый от нуля индекс. В следующем примере строка вставляется в пятую позицию индекса `MyString`, и создается новая строка с этим значением.  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### <a name="copyto"></a>CopyTo  
 Метод **String.CopyTo** копирует элементы строки в массив символов. Можно указать начальный индекс строки и число копируемых символов. Для копирования этому методу необходимы исходный индекс, массив знаков, индекс назначения и число символов. Все индексы отсчитываются от нуля.  
  
 В следующем примере мы используем метод **CopyTo**, чтобы скопировать символы слова Hello из строкового объекта в позицию первого индекса в массиве символов.  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## <a name="see-also"></a>См. также

- [Базовые операции со строками в .NET Framework](basic-string-operations.md)
- [Составное форматирование](composite-formatting.md)
