---
title: "コンパイラの警告 (レベル 1) C4655 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4655"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4655"
ms.assetid: 540f2c7a-e4a1-49af-84b4-03eeea1bbf41
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 1) C4655
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**'**   
 ***シンボル* ': 変数の型が前回のビルドから新規に追加されているか、他の個所で異なる定義がなされています**  
  
 前回成功したビルド以降に、新しいデータ型が変更または追加されています。 エディット コンティニュは、既存のデータ型への変更をサポートしません。  
  
 この警告の後に、[致命的なエラー C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md) が生成されます。 詳細については、「[サポートされているコード変更](../Topic/Supported%20Code%20Changes%20\(C++\).md)」を参照してください。  
  
### 現在のデバッグ セッションを終了せずにこの警告を削除するには  
  
1.  データ型をエラーが起こる前の状態に戻します。  
  
2.  **\[デバッグ\]** メニューの **\[コード変更を適用\]** をクリックします。  
  
### ソース コードを変更せずにこの警告を削除するには  
  
1.  **\[デバッグ\]** メニューの **\[デバッグの停止\]** をクリックします。  
  
2.  **\[ビルド\]** メニューの **\[ビルド\]** をクリックします。