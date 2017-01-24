---
title: "MFC のプロパティ シートとプロパティ ページ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コントロール [MFC], プロパティ シート"
  - "プロパティ ページ, MFC"
  - "プロパティ シート, MFC"
  - "タブ ダイアログ ボックス"
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC のプロパティ シートとプロパティ ページ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

タブ ダイアログ ボックスとも呼ばれるプロパティ シートは、プロパティ ページを持つダイアログ ボックスです。  各プロパティ ページはダイアログ テンプレート リソースに基づき、コントロールが含まれています。  これは上部タブのページで囲まれます。  タブの名前は、ページの目的を説明します。  ユーザーは、一連のコントロールを選択するには、プロパティ シートのタブをクリックします。  
  
 意味のある設定、プロパティ シートのコントロールをグループ化するためにページを使用します。  含まれているプロパティ シートに、独自の複数のコントロールがあります。  これらすべてのページに適用されます。  
  
 プロパティ シートは [CPropertySheet](../mfc/reference/cpropertysheet-class.md)クラスに基づいています。  プロパティ ページは [CPropertyPage](../mfc/reference/cpropertypage-class.md)クラスに基づいています。  
  
 プロパティ シートは、外部オブジェクトの属性を変更するためによく使用されるビューの現在の選択などのダイアログ ボックスを特別な型です。  プロパティ シートに 3 個の本体部分があります: 含むダイアログ ボックスは、そのページを選択するようにユーザーがクリックする各ページの上部にあるタブおよび一つずつ表示される一つ以上のプロパティ ページが表示されます。  プロパティ シートは、変更の設定またはオプションの同様のグループがある場合に便利です。  プロパティ シートは、わかりやすい方法で情報をグループ化します。  
  
> [!NOTE]
>  `CPropertySheet::DoModal`を使用してプロパティ シートを表示したりする場合に、システムは、初回例外を生成する可能性があります。  この例外は、オブジェクトが作成される前にオブジェクトの [ウィンドウ スタイル](../Topic/Window%20Styles.md) を変更しようとしているためです。  この例外の詳細については、それを回避または処理する方法を [CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md)を参照し。  
  
## 参照  
 [プロパティ シート](../mfc/property-sheets-mfc.md)