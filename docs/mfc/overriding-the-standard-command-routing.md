---
title: "標準のコマンド ルーティングのオーバーライド | Microsoft Docs"
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
  - "コマンド処理, ルーティング (コマンドを)"
  - "コマンド ルーティング, オーバーライド"
  - "MFC, コマンド ルーティング"
  - "オーバーライド, 標準コマンド ルーティング"
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 標準のコマンド ルーティングのオーバーライド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ほとんどの場合、標準フレームワーク ルーティングのバリエーションを実装しなければならないときにオーバーライドできます。  これは、そのクラスのオーバーライドの `OnCmdMsg` して一つ以上のクラスのルーティングを変更します。  結果:  
  
-   既定以外のオブジェクトに渡す順序を中断するクラス。  
  
-   の新しい既定以外のオブジェクトまたはコマンドの対象は、順番にコマンドを渡すこともあります。  
  
 ルーティングに新しいオブジェクトを挿入した場合、クラスはコマンドターゲット クラスである必要があります。  `OnCmdMsg`オーバーライドのバージョンでは、オーバーライドしているバージョンを呼び出すことを確認してください。  `CView` などのクラスの *MFC の参照* とバージョンのクラス `CCmdTarget` と例の指定したソース・コードの **CDocument** の [OnCmdMsg](../Topic/CCmdTarget::OnCmdMsg.md) メンバー関数を参照してください。  
  
## 参照  
 [フレームワークがハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)