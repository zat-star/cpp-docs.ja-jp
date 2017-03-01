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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 7b6a6220a33890d99e6fb2bd81ce832b38720c50
ms.lasthandoff: 02/24/2017

---
# <a name="adding-an-atl-property-page"></a>ATL プロパティ ページの追加
プロジェクトには、アクティブ テンプレート ライブラリ (ATL) のプロパティ ページを追加するにプロジェクト必要がありますが作成されたら、ATL アプリケーションまたは ATL サポートを持つ MFC アプリケーションとして。 使用することができます、 [ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)ATL アプリケーションを作成するか、 [ATL オブジェクトを MFC アプリケーションに追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)MFC アプリケーション用の ATL サポートを実装します。  
  
 コントロールがコントロールのプロパティ ページを追加する場合をサポートする必要があります、 [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)インターフェイスです。 このインターフェイスは、コントロールの派生リストで、既定では、クラス、 [ATL コントロールを作成する](../../atl/reference/adding-an-atl-control.md)を使用して、 [ATL コントロール ウィザード](../../atl/reference/atl-control-wizard.md)します。  
  
> [!NOTE]
>  コントロール クラスがない場合[ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)の派生リストにする必要があります手動で追加します。  
  
### <a name="to-add-an-atl-property-page-to-your-project"></a>ATL プロパティ ページをプロジェクトに追加するには  
  
1.  いずれかで**ソリューション エクスプ ローラー**または[クラス ビュー](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)、ATL プロパティ ページを追加するプロジェクトの名前を右クリックします。  
  
2.  ショートカット メニューをクリックして**追加** をクリックし、**クラスの追加**します。  
  
3.  [クラスの追加](../../ide/add-class-dialog-box.md)テンプレート ペインで、ダイアログ ボックスをクリックして**ATL プロパティ ページ** をクリックし、**開く**を表示する、 [ATL プロパティ ページ ウィザード](../../atl/reference/atl-property-page-wizard.md)します。  
  
 指定する必要があります、コントロールのプロパティ ページを作成すると、 [PROP_PAGE](http://msdn.microsoft.com/library/2155973e-b96c-4385-bf85-5d6112c969b8)コントロールのプロパティ マップ内のエントリ。  
  
## <a name="see-also"></a>関連項目  
 [プロパティ ページ](../../atl/atl-com-property-pages.md)   
 [ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)   
 [例: プロパティ ページの実装](../../atl/example-implementing-a-property-page.md)


