---
title: Использование переносимой библиотеки классов с шаблоном "модель-представление-модель представления"
ms.date: 07/18/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
ms.openlocfilehash: 2baa2aaa32c4138eee0932e5c46c2b52482007cd
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547562"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a>Использование переносимой библиотеки классов с шаблоном "модель-представление-модель представления"
Вы можете использовать .NET Framework [переносимую библиотеку классов](cross-platform-development-with-the-portable-class-library.md) для реализации шаблона модели представления "модель-представление-представление" (MVVM) и совместного использования сборок на нескольких платформах.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 MVVM — это шаблон приложения, который изолирует интерфейс пользователя от основной бизнес-логики. Классы модели и модели представления можно реализовать в проекте переносимой библиотеки классов в Visual Studio 2012, а затем создавать представления, настроенные для разных платформ. Такой подход позволяет писать модель данных и бизнес-логику только один раз и использовать этот код из приложений Магазина .NET Framework, Silverlight, Windows Phone и Windows 8. x, как показано на следующем рисунке.

 ![Показывает переносимую библиотеку классов с MVVM совместной работой сборок на разных платформах.](./media/using-portable-class-library-with-model-view-view-model/mvvm-share-assemblies-across-platforms.png)

 В этом разделе не приведены общие сведения о шаблоне MVVM. Он содержит только сведения об использовании переносимой библиотеки классов для реализации MVVM. Дополнительные сведения о MVVM см. в [кратком руководстве по MVVM с использованием библиотеки Prism 5,0 для WPF](/previous-versions/msp-n-p/gg430857(v=pandp.40)).

## <a name="classes-that-support-mvvm"></a>Классы, поддерживающие MVVM
 Если вы используете .NET Framework 4,5, .NET для приложений Магазина Windows 8. x, Silverlight или Windows Phone 7,5 для проекта переносимой библиотеки классов, для реализации шаблона MVVM доступны следующие классы:

- Класс <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>

- Класс <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>

- Класс <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType>

- Класс <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType>

- Класс <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType>

- Класс <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType>

- Класс <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType>

- Класс <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType>

- Класс <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType>

- Класс <xref:System.Windows.Input.ICommand?displayProperty=nameWithType>

- Все классы в <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> пространстве имен

## <a name="implementing-mvvm"></a>Реализация MVVM
 Для реализации MVVM обычно создается модель и модель представления в проекте переносимой библиотеки классов, поскольку проект переносимой библиотеки классов не может ссылаться на непереносимый проект. Модель и модель представления могут находиться в одном и том же проекте или в отдельных проектах. Если используются отдельные проекты, добавьте ссылку из проекта модели представления в проект модели.

 После компиляции модели и проектов модели представления вы ссылаетесь на эти сборки в приложении, которое содержит представление. Если представление взаимодействует только с моделью представления, необходимо ссылаться только на сборку, содержащую модель представления.

### <a name="model"></a>Моделирование
 В следующем примере показан упрощенный класс модели, который может находиться в проекте переносимой библиотеки классов.

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 В следующем примере показан простой способ заполнения, извлечения и обновления данных в проекте переносимой библиотеки классов. В реальных приложениях данные извлекаются из источника, например службы Windows Communication Foundation (WCF).

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a>Просмотр модели
 Базовый класс для моделей представления часто добавляется при реализации шаблона MVVM. В следующем примере показан базовый класс.

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 Реализация <xref:System.Windows.Input.ICommand> интерфейса часто используется с шаблоном MVVM. В следующем примере показана реализация интерфейса <xref:System.Windows.Input.ICommand>.

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 В следующем примере показана упрощенная модель представления.

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a>Просмотр  
 Из приложения .NET Framework 4,5, приложения Магазина Windows 8. x, приложения на основе Silverlight или приложения Windows Phone 7,5 можно ссылаться на сборку, содержащую проекты модели и представления модели.  Затем создается представление, взаимодействующее с моделью представления. В следующем примере показано упрощенное приложение Windows Presentation Foundation (WPF), которое извлекает и обновляет данные из модели представления. Аналогичные представления можно создавать в приложениях Магазина Silverlight, Windows Phone или Windows 8. x.  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a>См. также

- [Переносимая библиотека классов](cross-platform-development-with-the-portable-class-library.md)
