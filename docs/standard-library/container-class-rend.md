---
title: "コンテナー クラス::rend | Microsoft Docs"
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
  - "rend メソッド"
ms.assetid: 80f3dd04-dd2c-4b52-b0ed-d567ec5d186c
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンテナー クラス::rend
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  このトピックでは、標準 C\+\+ ライブラリで使用されるコンテナーの、機能的な例として、Visual C\+\+ のドキュメントにあります。  詳細については、「[STL コンテナー](../standard-library/stl-containers.md)」を参照してください。  
  
 このメンバー関数は、シーケンスの最初の要素を指す反転シーケンスの末尾を指定する反転反復子 \(または空のシーケンスの末尾の次の位置\) を返します。  
  
## 構文  
  
```  
  
      const_reverse_iterator rend( ) const;   
reverse_iterator rend( );  
```  
  
## 参照  
 [サンプル コンテナー クラス](../Topic/Sample%20Container%20Class.md)