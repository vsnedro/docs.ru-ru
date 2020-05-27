---
ms.openlocfilehash: 7a2617f27dfd6bb527ff6d408fae6382075f24ae
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83720986"
---
### <a name="typedescriptionproviderattribute-moved-to-another-assembly"></a>Класс TypeDescriptionProviderAttribute перенесен в другую сборку

Класс <xref:System.ComponentModel.TypeDescriptionProviderAttribute> перемещен.

#### <a name="change-description"></a>Описание изменений

В .NET Core 2.2 и более ранних версиях класс <xref:System.ComponentModel.TypeDescriptionProviderAttribute> находится в сборке *System.ComponentModel.TypeConverter*.

Начиная с .NET Core 3.0 он находится в сборке *System.ObjectModel*.

#### <a name="version-introduced"></a>Представленная версия

3,0

#### <a name="recommended-action"></a>Рекомендованное действие

Это изменение влияет только на приложения, использующие отражение для загрузки типа <xref:System.ComponentModel.TypeDescriptionProviderAttribute> путем вызова метода, такого как <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>, или перегрузки <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>, которая предполагает, что тип находится в определенной сборке. В этом случае сборку, указанную в вызове метода, необходимо обновить в соответствии с новым расположением сборки типа.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

Нет.

<!--

#### Affected APIs

- Not detectable via API analysis

-->
