---
ms.openlocfilehash: e42bce91afab68e509cb35a8992fa3ca2f096872
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496325"
---
### <a name="wpf-printing-stack-update"></a>Обновления стека печати WPF

#### <a name="details"></a>Подробнее

API-интерфейсы WPF для печати, использующие <xref:System.Printing.PrintQueue?displayProperty=fullName>, теперь вызывают API пакета печати документа Windows вместо устаревшего API печати XPS. Это изменение внесено в целях повышения удобства обслуживания. Ни пользователи, ни разработчики не должны заметить какие-либо изменения в поведении или использовании API. Новый стек печати по умолчанию активируется при работе с обновлением Windows 10 Creators Update. Старый стек печати по-прежнему будет работать в предыдущих версиях Windows, как и раньше.

#### <a name="suggestion"></a>Предложение

Чтобы использовать старый стек в Windows 10 Creators Update, задайте значение <code>UseXpsOMPrinting</code> REG_DWORD в разделе реестра <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> равным <code>1</code>.

| Имя    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.7|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
