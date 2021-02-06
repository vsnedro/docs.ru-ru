---
description: 'Дополнительные сведения о: My. Resources'
title: Объект My.Resources
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: ecd8e79aacea85080dc341ae36b362a595893034
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640632"
---
# <a name="myresources-object"></a>Объект My.Resources

Предоставляет свойства и классы для доступа к ресурсам приложения.  
  
## <a name="remarks"></a>Remarks  

 `My.Resources`Объект предоставляет доступ к ресурсам приложения и позволяет динамически получать ресурсы для приложения. Дополнительные сведения см. в разделе [Управление ресурсами приложения (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
 Объект `My.Resources` предоставляет только глобальные ресурсы. Он не предоставляет доступ к файлам ресурсов, связанным с формами. Вам нужно получить доступ к ресурсам формы из формы.  
  
 Доступ к файлам ресурсов для конкретного языка и региональных параметров приложения можно получить из `My.Resources` объекта. По умолчанию `My.Resources` объект ищет ресурсы из файла ресурсов, соответствующие языку и региональным параметрам в <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> свойстве. Однако это поведение можно переопределить и указать конкретный язык и региональные параметры, которые будут использоваться для ресурсов. Дополнительные сведения см. в разделе [Ресурсы в приложениях для настольных систем](../../../framework/resources/index.md).  
  
## <a name="properties"></a>Свойства  

 Свойства `My.Resources` объекта предоставляют доступ только для чтения к ресурсам приложения. Чтобы добавить или удалить ресурсы, используйте **Конструктор проектов**. Доступ к ресурсам, добавленным с помощью **конструктора проектов** , можно получить с помощью `My.Resources.` *resourceName*.  
  
 Можно также добавлять или удалять файлы ресурсов, выбрав проект в **Обозреватель решений** и выбрав пункт **Добавить новый элемент** или **Добавить существующий элемент** в меню **проект** . Доступ к ресурсам, добавленным таким способом, можно получить с помощью `My.Resources.` *ресаурцефиленаме* `.` *resourceName*.  
  
 Каждый ресурс имеет имя, категорию и значение, и эти параметры ресурсов определяют, как свойство для доступа к ресурсу отображается в `My.Resources` объекте. Для ресурсов, добавленных в **конструкторе проектов**:  
  
- Имя определяет имя свойства,  
  
- Данные ресурса являются значением свойства,  
  
- Категория определяет тип свойства:  
  
|Категория|Тип данных свойства|  
|---|---|  
|**Строки**|[String](../data-types/string-data-type.md)|  
|**Изображения**|<xref:System.Drawing.Bitmap>|  
|**Значки**|<xref:System.Drawing.Icon>|  
|**звук;**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> <xref:System.IO.UnmanagedMemoryStream>Класс является производным от <xref:System.IO.Stream> класса, поэтому его можно использовать с методами, принимающими потоки, например <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> метод.|  
|**Файлы**|-   [Строка](../data-types/string-data-type.md) для текстовых файлов.<br />-   <xref:System.Drawing.Bitmap> для файлов изображений.<br />-   <xref:System.Drawing.Icon> для файлов значков.<br />-   <xref:System.IO.UnmanagedMemoryStream> для звуковых файлов.|  
|**Другое**|Определяется сведениями в столбце **типа** конструктора.|  
  
## <a name="classes"></a>Классы  

 `My.Resources`Объект предоставляет каждый файл ресурсов как класс с общими свойствами. Имя класса совпадает с именем файла ресурсов. Как описано в предыдущем разделе, ресурсы в файле ресурсов предоставляются как свойства в классе.  
  
## <a name="example"></a>Пример  

 В этом примере задается заголовок формы в виде строкового ресурса, указанного `Form1Title` в файле ресурсов приложения. Чтобы пример работал, приложение должно иметь строку с именем `Form1Title` в файле ресурсов.  
  
 [!code-vb[VbVbalrMyResources#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#1)]  
  
## <a name="example"></a>Пример  

 В этом примере значок формы задается значком с именем `Form1Icon` , который хранится в файле ресурсов приложения. Чтобы пример работал, приложение должно иметь `Form1Icon` в своем файле ресурсов значок с именем.  
  
 [!code-vb[VbVbalrMyResources#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#2)]  
  
## <a name="example"></a>Пример  

 В этом примере для фонового изображения формы задается ресурс изображения с именем `Form1Background` , который находится в файле ресурсов приложения. Чтобы этот пример работал, приложение должно иметь ресурс образа с именем `Form1Background` в файле ресурсов.  
  
 [!code-vb[VbVbalrMyResources#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#3)]  
  
## <a name="example"></a>Пример  

 В этом примере воспроизводится звук, который хранится в виде звукового ресурса `Form1Greeting` в файле ресурсов приложения. Чтобы пример работал, в файле ресурсов приложения должен быть указан звуковой ресурс `Form1Greeting` . `My.Computer.Audio.Play`Метод доступен только для приложений Windows Forms.  
  
 [!code-vb[VbVbalrMyResources#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#4)]  
  
## <a name="example"></a>Пример  

 В этом примере извлекается версия строкового ресурса приложения на французском языке. Ресурс называется `Message` . Для изменения языка и региональных параметров, `My.Resources` используемых объектом, в примере используется <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A> .  
  
 Для работы этого примера приложение должно иметь строку с именем `Message` в файле ресурсов, а приложение должно иметь версию файла ресурсов для французского языка и региональных параметров Resources.fr-FR. resx. Если приложение не имеет версию файла ресурсов для французского языка и региональных параметров, `My.Resource` объект получает ресурс из файла ресурсов языка и региональных параметров по умолчанию.  
  
 [!code-vb[VbVbalrMyResources#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#10)]  
  
## <a name="see-also"></a>См. также

- [Управление ресурсами приложения (.NET)](/visualstudio/ide/managing-application-resources-dotnet)
- [Ресурсы в приложениях для настольных систем](../../../framework/resources/index.md)
