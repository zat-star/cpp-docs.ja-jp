---
title: "テクニカル ノート 32: MFC 例外処理機構 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.exceptions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CException クラス, 使用"
  - "MFC, 例外"
  - "TN032"
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# テクニカル ノート 32: MFC 例外処理機構
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

以前のバージョンの Visual C\+\+ では、標準 C\+\+ 例外機構と代わりに使用された MFC に用意されたマクロ **TRY\/CATCH\/THROW** をサポートしていません。  Visual C\+\+ のこのバージョンは、C\+\+ 例外処理をサポートします。  ここではどのようにクリーンアップのスタックでベース オブジェクトを含む前のマクロの高度な実装の詳細に自動的について説明しました。  既定では、アンワインドする C\+\+ 例外処理サポート スタックがこのテクニカル ノート不要になったため。  
  
 MFC マクロと新しい C\+\+ キーワードの違いの詳細については [例外: MFC マクロと C\+\+ 例外を使用する](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) "を参照してください。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)