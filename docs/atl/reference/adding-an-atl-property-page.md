---
title: "ATL プロパティ ページの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 72a8644d81857b722fd50a7e852d215bb25a2fb2
ms.lasthandoff: 03/31/2017

---
# <a name="adding-an-atl-property-page"></a>ATL プロパティ ページを追加します。
プロジェクトに、アクティブ テンプレート ライブラリ (ATL) のプロパティ ページを追加するには、プロジェクト必要がありますを作成して、ATL アプリケーションまたは ATL サポートを含む MFC アプリケーションとして。 使用することができます、 [ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)ATL アプリケーションを作成するか、 [ATL オブジェクトを MFC アプリケーションに追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)MFC アプリケーションに対する ATL のサポートを実装します。  
  
 コントロールのプロパティ ページを追加する場合、コントロールをサポートする必要があります、 [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)インターフェイスです。 このインターフェイスは、コントロールの派生リストで、既定では、クラスを[ATL コントロールを作成する](../../atl/reference/adding-an-atl-control.md)を使用して、 [ATL コントロール ウィザード](../../atl/reference/atl-control-wizard.md)です。  
  
> [!NOTE]
>  コントロール クラスがない場合[ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)の派生リストにする必要があります手動で追加します。  
  
### <a name="to-add-an-atl-property-page-to-your-project"></a>プロジェクトに ATL プロパティ ページを追加するには  
  
1.  いずれかで**ソリューション エクスプ ローラー**または[クラス ビュー](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)、ATL プロパティ ページを追加するプロジェクトの名前を右クリックします。  
  
2.  ショートカット メニューから [**追加**] をクリックし、**クラスの追加**です。  
  
3.  [クラスの追加](../../ide/add-class-dialog-box.md)ダイアログ ボックスの [テンプレート] ペインで、クリックして**ATL プロパティ ページ**順にクリック**開く**を表示する、 [ATL プロパティ ページ ウィザード](../../atl/reference/atl-property-page-wizard.md)です。  
  
 コントロールのプロパティ ページを作成すると、指定する必要あります、 [PROP_PAGE](property-map-macros.md#prop_page)コントロールのプロパティ マップ内のエントリ。  
  
## <a name="see-also"></a>関連項目  
 [プロパティ ページ](../../atl/atl-com-property-pages.md)   
 [ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)   
 [例: プロパティ ページの実装](../../atl/example-implementing-a-property-page.md)


