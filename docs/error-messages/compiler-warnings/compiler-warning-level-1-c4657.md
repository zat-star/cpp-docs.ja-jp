---
title: "コンパイラの警告 (レベル 1) C4657 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4657"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4657"
ms.assetid: eb750050-cea6-4ead-b80c-d5dcd4971cfc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 1) C4657
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

前回のビルド以降新規に追加されたデータ型が数式に含まれています  
  
 前回成功したビルド以降に、データ型が追加されたか既存のデータ型が変更されました。これは、今までソース コードに含まれていなかったデータ型です。 エディット コンティニュは、既存のデータ型への変更をサポートしません。  
  
 この警告の後に必ず[致命的なエラー C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md) が生成されます。 詳細については、「[サポートされているコード変更](../Topic/Supported%20Code%20Changes%20\(C++\).md)」を参照してください。  
  
### 現在のデバッグ セッションを終了せずにこの警告を削除するには  
  
1.  データ型をエラーが起こる前の状態に戻します。  
  
2.  **\[デバッグ\]** メニューの **\[コード変更を適用\]** をクリックします。  
  
### ソース コードを変更せずにこのエラーを削除するには  
  
1.  **\[デバッグ\]** メニューの **\[デバッグの停止\]** をクリックします。  
  
2.  **\[ビルド\]** メニューの **\[ビルド\]** をクリックします。