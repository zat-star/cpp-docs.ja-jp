---
title: "印刷 | Microsoft Docs"
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
  - "ドキュメント, 印刷"
  - "印刷 [MFC]"
  - "印刷 [MFC], フレームワークから"
  - "ビュー クラス, 印刷処理"
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 印刷
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Windows の実装のデバイスに依存しない表示。  MFC では、これは、ビュー クラスの `OnDraw` メンバー関数を同じ描画呼び出しが、表示とそのほかのデバイスに描画を行うことです。プリンターなど\)。  印刷プレビュー用に、ターゲット デバイスが表示にシミュレートされたプリンター出力です。  
  
##  <a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a> 印刷のロールとフレームワークの役割  
 ビュー クラスに次の必要があります:  
  
-   ページ数をドキュメントにあるかフレームワークを通知します。  
  
-   指定したページを印刷を求められたときにドキュメントのその部分を描画します。  
  
-   印刷に必要なフォントやグラフィック デバイス インターフェイス \(GDI\) の他のリソースの割り当てと解放してください。  
  
-   必要に応じて、ページなどをページごとの印刷方向を変更するには、印刷前にプリンターのモードを変更するには、必要なエスケープ コードを指定します。  
  
 フレームワークの役割は次のとおりです。:  
  
-   **印刷** ダイアログ ボックスを表示します。  
  
-   プリンターの [CDC](../Topic/CDC%20Class.md) オブジェクトを作成します。  
  
-   `CDC` オブジェクトの [StartDoc](../Topic/CDC::StartDoc.md) と [EndDoc](../Topic/CDC::EndDoc.md) メンバー関数を呼び出します。  
  
-   すべてのページが印刷される呼び出し `CDC` オブジェクトの [EndPage](../Topic/CDC::EndPage.md) のメンバー関数を呼び出して、または繰り返し `CDC` オブジェクトの [StartPage](../Topic/CDC::StartPage.md) メンバー関数を、通知ビュー クラスを示します。  
  
-   適切なタイミングでビューのオーバーライドできるな関数を呼び出します。  
  
 次のトピックは、フレームワークが印刷と印刷プレビューをどのようにサポートするかについて説明します。:  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [既定の印刷がどのように行われるか](../Topic/How%20Default%20Printing%20Is%20Done.md)  
  
-   [複数ページのドキュメント](../mfc/multipage-documents.md)  
  
-   [ヘッダーとフッター](../mfc/headers-and-footers.md)  
  
-   [印刷の GDI のリソースを割り当てます。](../mfc/allocating-gdi-resources.md)  
  
-   [印刷プレビュー](../mfc/print-preview-architecture.md)  
  
## 参照  
 [印刷および印刷プレビュー](../mfc/printing-and-print-preview.md)