---
title: "ADO データ コントロールでデータを更新する | Microsoft Docs"
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
  - "ADO [C++], データ バインド"
  - "ADO [C++], データ コントロール"
ms.assetid: 8bec34b9-93dd-4872-b023-55ac011ccff5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ADO データ コントロールでデータを更新する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ADO データ コントロールのデータは、読み取り専用にすることも、変更可能にすることもできます。  
  
### ADO データ コントロールを使用してデータを変更するアプリケーションを作成するには  
  
1.  ADO データ コントロールの **CursorLocation** プロパティを設定します。  次のオプションがあります。  
  
    -   Server Side  
  
    -   Client Side  
  
2.  ADO データ コントロールの **LockType** プロパティを設定します。  オプティミスティック同時実行制御をお勧めします。  
  
3.  ADO データ コントロールの **CursorType** プロパティを設定します。  次のオプションがあります。  
  
    -   Keyset Cursor  
  
    -   Dynamic Cursor  
  
    -   Static Cursor  
  
     OLE DB プロバイダーが、選択したオプションをサポートしていることを確認してください。  
  
4.  必要に応じて、データ バインド コントロールのプロパティを更新可能に設定します。  更新可能にできないコントロールもあります。  
  
 これらのプロパティの詳細については、ADO のドキュメントを参照してください。  
  
## 参照  
 [ADO データ バインド](../../data/ado-rdo/ado-databinding.md)   
 [Visual C\+\+ で ADO データ バインドを使用する](../../data/ado-rdo/using-ado-databinding-in-visual-cpp.md)