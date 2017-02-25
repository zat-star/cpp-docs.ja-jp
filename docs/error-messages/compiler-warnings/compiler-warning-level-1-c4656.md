---
title: "コンパイラの警告 (レベル 1) C4656 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4656"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4656"
ms.assetid: b5aaef74-2320-4345-a6ae-b813881a491c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 1) C4656
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : データ型は前回のビルドから新規に追加、変更されているか、他の個所で異なる定義がなされています。  
  
 前回成功したビルド以降に、データ型がソース コードに追加されたか、または既存のデータ型が変更されています。  エディット コンティニュは、既存のデータ型への変更をサポートしません。  
  
 この警告の後に必ず[致命的なエラー C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md) が生成されます。  詳細については、「[サポートされているコード変更](../Topic/Supported%20Code%20Changes%20\(C++\).md)」を参照してください。  
  
### 現在のデバッグ セッションを終了しないでこの警告を解除するには  
  
1.  データ型をエラーが起こる前の状態に戻します。  
  
2.  \[デバッグ\] メニューの \[コード変更を適用\] をクリックします。  
  
### ソース コードを変更せずにこのエラーを取り除くには  
  
1.  **\[デバッグ\]** メニューの **\[デバッグの停止\]** をクリックします。  
  
2.  **\[ビルド\]** メニューの **\[ビルド\]** をクリックします。