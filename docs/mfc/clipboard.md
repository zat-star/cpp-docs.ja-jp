---
title: "クリップボードのトピック | Microsoft Docs"
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
  - "クリップボードのトピック"
  - "クリップボードのトピック, プログラミング"
  - "コピー (データを)"
  - "切り取りとコピー (データを)"
  - "転送 (データを)"
ms.assetid: a71b2824-1f14-4914-8816-54578d73ad4e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# クリップボードのトピック
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、MFC アプリケーションで Windows クリップボードのサポートを実装する方法について説明します。  Windows クリップボードは 2 とおりの方法で使用されています:  
  
-   標準を実装して切り取り、コピー、および貼り付けなどのメニュー コマンドを編集します。  
  
-   ドラッグ アンド ドロップを含む汎用データ転送 \(OLE\) 実装。  
  
 クリップボードは、ソースとターゲット間でデータを転送する標準のメソッドです。  また、OLE 操作に非常に便利です。  OLE の発展のウィンドウに 2 個のクリップボード機能があります。  標準の Windows クリップボード API は使用できますが、OLE データ転送の機能によって補われました。  OLE 汎用データ転送 \(UDT\) は、クリップボード操作やドラッグ アンド ドロップを使用して切り取り、コピー、および貼り付けをサポートします。  
  
 クリップボードはすべての Windows セッションで共有されるシステム サービスであるため、独自のハンドルやクラスがありません。  [CWnd](../Topic/CWnd%20Class.md)クラスのメンバー関数によってクリップボードを管理します。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [いつ各クリップボード機能を使用できます。](../mfc/clipboard-when-to-use-each-clipboard-mechanism.md)  
  
-   [従来の Windows クリップボード API を使用して](../mfc/clipboard-using-the-windows-clipboard.md)  
  
-   [OLE のクリップボード機能を使用する](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
-   [データのコピーと貼り付け](../Topic/Clipboard:%20Copying%20and%20Pasting%20Data.md)  
  
-   [そのほかの形式の追加](../mfc/clipboard-adding-other-formats.md)  
  
-   [\<caps:sentence id\="tgt18" sentenceid\="1bc8aafd7da110d0b343b54cffa169d9" class\="tgtSentence"\>Windows クリップボード\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms648709)  
  
-   [ドラッグ アンド ドロップを実装します \(OLE\)](../mfc/drag-and-drop-ole.md)  
  
## 参照  
 [ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)