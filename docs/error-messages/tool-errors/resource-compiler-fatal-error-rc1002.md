---
title: "リソース コンパイラの致命的なエラー RC1002 | Microsoft Docs"
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
  - "RC1002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1002"
ms.assetid: b43dfece-0dc3-4d0b-9d8f-509699b9ae80
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リソース コンパイラの致命的なエラー RC1002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ヒープ スペースがありません。  
  
### 次のような解決策を使用して問題を解決するには  
  
1.  Windows のスワップ ファイルの容量を増やします。  スワップ ファイルの容量を増やす方法の詳細については、Windows ヘルプの仮想メモリに関するトピックを参照してください。  
  
2.  現在のファイルを複数のより小さいファイルに分割し、それぞれをコンパイルします。  
  
3.  システムで実行されている、ほかのプログラムまたはドライバーを削除します。