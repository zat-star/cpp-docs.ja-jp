---
title: "ATL プロパティ ページの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: abf50e98d32789e357f5e13339ee2fc0a0daa331
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-atl-property-page"></a>ATL プロパティ ページを追加します。
プロジェクトに、アクティブ テンプレート ライブラリ (ATL) のプロパティ ページを追加するには、プロジェクト必要がありますを作成して、ATL アプリケーションまたは ATL サポートを含む MFC アプリケーションとして。 使用することができます、 [ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)ATL アプリケーションを作成するか、 [ATL オブジェクトを MFC アプリケーションに追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)MFC アプリケーションに対する ATL のサポートを実装します。  
  
 コントロールのプロパティ ページを追加する場合、コントロールをサポートする必要があります、 [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)インターフェイスです。 このインターフェイスは、コントロールの派生リストで、既定では、クラスを[ATL コントロールを作成する](../../atl/reference/adding-an-atl-control.md)を使用して、 [ATL コントロール ウィザード](../../atl/reference/atl-control-wizard.md)です。  
  
> [!NOTE]
>  コントロール クラスがない場合[ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)の派生リストにする必要があります手動で追加します。  
  
### <a name="to-add-an-atl-property-page-to-your-project"></a>プロジェクトに ATL プロパティ ページを追加するには  
  
1.  いずれかで**ソリューション エクスプ ローラー**または[クラス ビュー](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)、ATL プロパティ ページを追加するプロジェクトの名前を右クリックします。  
  
2.  ショートカット メニューから **[追加]** をクリックし、**クラスの追加**です。  
  
3.  [クラスの追加](../../ide/add-class-dialog-box.md)ダイアログ ボックスの [テンプレート] ペインで、クリックして**ATL プロパティ ページ** をクリックし、**開く**を表示する、 [ATL プロパティ ページ ウィザード](../../atl/reference/atl-property-page-wizard.md).  
  
 コントロールのプロパティ ページを作成すると、指定する必要あります、 [PROP_PAGE](property-map-macros.md#prop_page)コントロールのプロパティ マップ内のエントリ。  
  
## <a name="see-also"></a>参照  
 [プロパティ ページ](../../atl/atl-com-property-pages.md)   
 [ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)   
 [例: プロパティ ページの実装](../../atl/example-implementing-a-property-page.md)

