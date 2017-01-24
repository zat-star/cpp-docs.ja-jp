---
title: "ジェネリック メソッドで &#39;Handles&#39; 句を使用することはできません | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32080"
  - "BC32080"
helpviewer_keywords: 
  - "BC32080"
ms.assetid: 88c62a1c-aee3-46b2-ad78-76790022c04c
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ジェネリック メソッドで &#39;Handles&#39; 句を使用することはできません
ジェネリック `Sub` プロシージャの宣言には、[Handles](../Topic/Handles%20Clause%20\(Visual%20Basic\).md) 句が含まれます。  
  
 `Handles` 句は、`Sub` プロシージャが処理するイベントの一覧を指定します。 イベント ハンドラーとなるには、`Sub` プロシージャに、処理する各イベントと同じシグネチャがなければなりません。 ジェネリック プロシージャを複数回作成できますが、使用するシグネチャに関してはコンパイル時に [!INCLUDE[vbprvb](../Token/vbprvb_md.md)] が予測することはできません。 したがって、`Handles` 句の中のイベントと一致するシグネチャを [!INCLUDE[vbprvb](../Token/vbprvb_md.md)] が保証することはできません。  
  
 **エラー ID:** BC32080  
  
### このエラーを解決するには  
  
-   `Sub` プロシージャがジェネリックである必要がある場合、宣言から `Handles` 句を削除してください。[AddHandler Statement](../Topic/AddHandler%20Statement.md) を使用して、このイベント ハンドラーをイベントに関連付けます。  
  
-   `Sub` プロシージャが `Handles` 句を使用してイベントを関連付ける必要がある場合には、宣言から [Of](../Topic/Of%20Clause%20\(Visual%20Basic\).md) 句を削除します。`Handles` と一緒に非ジェネリック プロシージャを使用しなければなりません。  
  
## 参照  
 [Visual Basic におけるジェネリック型](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [ビルド内にありません: イベントとイベント ハンドラー](http://msdn.microsoft.com/ja-jp/95074a0d-1cbc-4221-a95a-964185c7f962)