---
title: "ビューのスクロールと拡大/縮小 | Microsoft Docs"
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
  - "メッセージ ハンドラー"
  - "メッセージ処理, スクロール バー (ビュー クラスの)"
  - "拡大/縮小 (ビューを)"
  - "スクロール バー, メッセージ"
  - "スクロール可能なビュー"
ms.assetid: f98a3421-c336-407e-97ee-dbb2ffd76fbd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ビューのスクロールと拡大/縮小
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC に表示するフレーム ウィンドウのサイズが自動的にスケーリングされるビュー、スクロール ビューをサポートします。  クラス `CScrollView` はどちらのビューをサポートしています。  
  
 スクロールやスケーリングに関する詳細については、" *MFC リファレンス"の*" [CScrollView](../mfc/reference/cscrollview-class.md) クラスを参照します。  スクロールの例については、[Scribble サンプル](../top/visual-cpp-samples.md)を参照してください。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   ビューのスクロール  
  
-   ビューの拡大  
  
-   [\<caps:sentence id\="tgt8" sentenceid\="f321fcf7c88bc6e3f892ae0fc9b2f0d8" class\="tgtSentence"\>ビュー座標\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd145205)  
  
##  <a name="_core_scrolling_a_view"></a> ビューのスクロール  
 多くの場合、文書のサイズはサイズが大きく表示できるビューです。  これはドキュメント データを生成したり、ユーザーがビューを構築するウィンドウを縮小するときに発生する可能性があります。  このような場合、スクロールをサポートする必要があります。  
  
 どのビューで `OnHScroll` と `OnVScroll` のメンバー関数のスクロール バー メッセージを処理できます。  これらの関数のスクロール バー メッセージの処理をすると、すべての作業を自分で実装するか、のスクロールを処理するために `CScrollView` クラスを使用できます。  
  
 `CScrollView` は、次の処理を行います。  
  
-   ウィンドウ、およびビューポートのサイズとマップ モード管理します。  
  
-   自動的にスクロール バー メッセージへの応答  
  
 \(ユーザーがスクロール バーの矢印ボタンをクリックしたときに\) 」または「ページのスクロールする量指定し、\(ユーザーがスクロール バー シャフトでクリックしたときに「row」\)。  ビューの性質に合うようにこれらの値を計画します。  たとえば、グラフィックスのビューの 1 ピクセル単位でテキスト ドキュメントの行の高さに基づいてインクリメントにスクロールする場合があります。  
  
##  <a name="_core_scaling_a_view"></a> ビューの拡大  
 ビューに自動的にフレーム ウィンドウのサイズに合わせる必要とスクロールの代わりにスケーリングに `CScrollView` を使用できます。  論理ビューは、ウィンドウのクライアント領域に完全に収まるように拡張または縮小。  スケーリングされたスクロール バーはありません。  
  
## 参照  
 [ビューの使い方](../mfc/using-views.md)