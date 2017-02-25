---
title: "コマンド ライン エラー D8027 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D8027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D8027"
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コマンド ライン エラー D8027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'component'を実行できません。  
  
 メッセージに示されているコンパイラのコンポーネントまたはリンカーを実行できません。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  メモリ不足のため、このコンポーネントを読み込めません。  NMAKE からコンパイラを起動した場合は、メイクファイルを使用せずにコンパイラを実行してください。  
  
2.  使用中のオペレーティング システムでは、このコンポーネントを実行できません。  実行可能ファイルのパスに、使用中のオペレーティング システムに適したファイルが指定されているかどうかを確認してください。  
  
3.  このコンポーネントは破損しています。  SETUP プログラムを実行し、このコンポーネントをパッケージ内のディスクからコピーし直してください。  
  
4.  オプションの指定が間違っています。  たとえば、次のようになります。  
  
    ```  
    cl /B1 file1.c  
    ```