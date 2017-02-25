---
title: "モードレス プロパティ シートの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Create メソッド [C++], プロパティ シート"
  - "モードレス プロパティ シート"
  - "プロパティ シート, モードレス"
ms.assetid: eafd8a92-cc67-4a69-a5fb-742c920d1ae8
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# モードレス プロパティ シートの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

通常、作成するプロパティ シートはモーダルです。  モーダル プロパティ シートを使用すると、ユーザーはアプリケーションのほかの部分を使用する前に、プロパティ シートを閉じる必要があります。  ここでは、プロパティ シートを作成するためのモードレス プロパティ シートを作成するために使用できるメソッドについて説明します。アプリケーションの他の部分を使用します。  
  
 モーダル ダイアログ ボックスとしてではなく、モードレス ダイアログ ボックスとしてプロパティ シートを表示するには、[DoModal](../Topic/CPropertySheet::DoModal.md)の代わりに [CPropertySheet::Create](../Topic/CPropertySheet::Create.md) を呼び出します。  また、モードレス プロパティ シートをサポートする追加のタスクを実装しなければなりません。  
  
 追加のタスクの 1 つがプロパティ シートが開くときに変更する外部オブジェクトとプロパティ シートとのデータ交換です。  これは、通常、標準モードレス ダイアログ ボックスのと同じタスクです。  このタスクの一部は、プロパティ設定を適用する外部オブジェクトとモードレス プロパティ シートの間の通信チャネルを実装しています。  この実装は、モードレス プロパティ シートの [CPropertySheet](../mfc/reference/cpropertysheet-class.md) からクラスを派生すればはるかに簡単です。  ここでは、そうしたとします。  
  
 モードレス プロパティ シートと外部オブジェクト \(ビューの現在の選択項目の間で通信するための 1 種類のメソッドは、たとえば\) プロパティ シートの外部オブジェクトへのポインターを定義することです。  `CPropertySheet`\- 1 個の外部オブジェクトから別の要素へのポインターをいつでもフォーカス変更変更した派生クラスの関数 \(`SetMyExternalObject`のようなものと呼ばれる\) を定義します。  `SetMyExternalObject` 関数は、最近選択した外部オブジェクトを反映するプロパティ ページの設定をリセットする必要があります。  これを行うには、`SetMyExternalObject` 関数は `CPropertySheet` クラスに属する [CPropertyPage](../mfc/reference/cpropertypage-class.md) オブジェクトにアクセスできる必要があります。  
  
 プロパティ シート内のプロパティ ページへのアクセスを提供する最も簡単な方法は、\-派生オブジェクトを `CPropertySheet`で `CPropertyPage` オブジェクト埋め込むことです。  `CPropertyPage` を埋め込みます `CPropertySheet`でオブジェクトを\-派生オブジェクトは、プロパティ シートの所有者が `CPropertyPage` オブジェクトを作成し、プロパティ シートに [CPropertySheet::AddPage](../Topic/CPropertySheet::AddPage.md)で渡すモーダル ダイアログ ボックスの一般的なデザインとは異なります。  
  
 モードレス プロパティ シートの設定は、外部オブジェクトに適用するかを決定するための各種のユーザー インターフェイスの方法があります。  1 種類の代わりに、たびにユーザーが変更された値は、現在のプロパティ ページの設定を適用することです。  別の方法としては、ユーザーが外部オブジェクトにコミットされる前にプロパティ ページを収集できるようにする適用ボタンを提供することです。  適用ボタンを処理する方法については、[適用ボタンの処理](../mfc/handling-the-apply-button.md)記事を参照してください。  
  
## 参照  
 [プロパティ シート](../mfc/property-sheets-mfc.md)   
 [データの交換](../mfc/exchanging-data.md)   
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)