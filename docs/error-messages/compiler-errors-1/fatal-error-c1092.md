---
title: "致命的なエラー C1092 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1092"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1092"
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1092
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

エディット コンティニュはデータ型への変更をサポートしません。ビルドが必要です。  
  
 前回の成功したビルド以降に、データ型が変更または追加されています。  
  
-   エディット コンティニュは、クラス、構造体、または列挙型の定義も含め、既存のデータ型への変更をサポートしません。  デバッグを中断して、アプリケーションをビルドする必要があります。  
  
-   vc*x*0.pdb \(*x* は使用中の Visual C\+\+ のメジャー バージョン\) などのプログラム データベース ファイルが読み取り専用の場合、エディット コンティニュは新しいデータ型の追加をサポートしません。  データ型を追加するには、コンパイラで .pdb ファイルを書き込みモードで開く必要があります。  
  
### 現在のデバッグ セッションを終了せずにこのエラーを解除するには  
  
1.  データ型をエラーが起こる前の状態に戻します。  
  
2.  **\[デバッグ\]** メニューの **\[コード変更を適用\]** をクリックします。  
  
### ソース コードを変更せずにこのエラーを取り除くには  
  
1.  **\[デバッグ\]** メニューの **\[デバッグの停止\]** をクリックします。  
  
2.  **\[ビルド\]** メニューの **\[ビルド\]** をクリックします。  
  
 詳細については、「[サポートされているコード変更](../Topic/Supported%20Code%20Changes%20\(C++\).md)」を参照してください。