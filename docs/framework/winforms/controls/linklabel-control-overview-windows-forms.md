---
title: Общие сведения об элементе управления LinkLabel
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 3e8607644c858ae804e384c974b5e81c1786c6a1
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739516"
---
# <a name="linklabel-control-overview-windows-forms"></a>Общие сведения об элементе управления LinkLabel (Windows Forms)
Элемент управления <xref:System.Windows.Forms.LinkLabel> Windows Forms позволяет добавлять ссылки в веб-стиле в приложения Windows Forms. Вы можете <xref:System.Windows.Forms.LinkLabel> использовать элемент управления для <xref:System.Windows.Forms.Label> всего, что вы можете использовать элемент управления для; вы также можете установить часть текста в виде ссылки на файл, папку или веб-страницу.  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>Что вы можете сделать с помощью управления LinkLabel  
 В дополнение ко всем свойствам, методам <xref:System.Windows.Forms.Label> и событиям <xref:System.Windows.Forms.LinkLabel> управления, элемент управления имеет свойства для гиперссылок и цветов связи. Свойство <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> устанавливает область текста, которая активирует ссылку. В <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> и свойства установить цвета ссылки. Событие <xref:System.Windows.Forms.LinkLabel.LinkClicked> определяет, что происходит при выборе текста ссылки.  
  
 Простейшая цель <xref:System.Windows.Forms.LinkLabel> управления — отобразить <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> единую ссылку с помощью свойства, но вы также можете отображать несколько гиперссылок с помощью <xref:System.Windows.Forms.LinkLabel.Links%2A> свойства. Свойство <xref:System.Windows.Forms.LinkLabel.Links%2A> позволяет получить доступ к коллекции ссылок. Вы также можете указать данные в свойстве <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> каждого отдельного <xref:System.Windows.Forms.LinkLabel.Link> объекта. Значение <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> свойства может быть использовано для хранения местоположения файла для отображения или адреса веб-узла.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.LinkLabel>
- [Общие сведения об элементе управления Label](label-control-overview-windows-forms.md)
- [Практическое руководство. Создание связи с объектом или веб-страницей с помощью элемента управления LinkLabel в Windows Forms](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
