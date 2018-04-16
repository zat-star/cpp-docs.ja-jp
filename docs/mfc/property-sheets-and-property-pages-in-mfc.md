---
title: "プロパティ シートとプロパティ ページ (MFC の) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- property pages [MFC], MFC
- controls [MFC], property sheets
- property sheets, MFC
- tab dialog boxes
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24a66bf9e062e43225827afdbb0bba45511c5f13
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="property-sheets-and-property-pages-in-mfc"></a>MFC のプロパティ シートとプロパティ ページ
タブ ダイアログ ボックスとも呼ばれるプロパティ シートは、プロパティ ページを含むダイアログ ボックスです。 各プロパティ ページでは、ダイアログ テンプレート リソースに基づいており、コントロールが含まれています。 上部のタブで、ページに囲まれています。 タブ、ページの名前をその目的を示します。 ユーザーは、コントロールのセットを選択するプロパティ シートのタブをクリックします。  
  
 プロパティ シート内のコントロールに意味のあるセットをグループ化するのにには、ページを使用します。 包含プロパティ シートには、通常、独自のいくつかのコントロールがあります。 これらは、すべてのページに適用されます。  
  
 プロパティ シートは、クラスに基づく[CPropertySheet](../mfc/reference/cpropertysheet-class.md)です。 プロパティ ページは、クラスに基づく[CPropertyPage](../mfc/reference/cpropertypage-class.md)です。  
  
 プロパティ シートは、ビューの現在の選択など、いくつかの外部オブジェクトの属性を変更するのには通常、使用する ダイアログ ボックスの特別な種類です。 プロパティ シートには次の 3 つの主要な部分: を含むダイアログ ボックスで、1 つまたは複数のプロパティ ページを示す 1 つずつ、およびそのページを選択するユーザーがクリックした各ページの上部にあるタブ。 プロパティ シートは、設定または変更するオプションのいくつかのようなグループがある場合に便利です。 プロパティ シートでは、わかりやすい方法で情報をグループ化します。  
  
> [!NOTE]
>  使用して、プロパティ シートを表示しようと`CPropertySheet::DoModal`システムは初回例外を生成する可能性があります。 システムが変更をしようとしているために、この例外が発生した、[ウィンドウ スタイル](../mfc/reference/styles-used-by-mfc.md#window-styles)オブジェクトが作成される前に、オブジェクトの。 これを回避または処理する方法と、この例外の詳細については、次を参照してください。[する](../mfc/reference/cpropertysheet-class.md#domodal)です。  
  
## <a name="see-also"></a>参照  
 [プロパティ シート](../mfc/property-sheets-mfc.md)

