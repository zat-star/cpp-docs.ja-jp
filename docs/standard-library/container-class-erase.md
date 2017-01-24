---
title: "コンテナー クラス::erase | Microsoft Docs"
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
  - "erase メソッド"
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンテナー クラス::erase
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  このトピックでは、標準 C\+\+ ライブラリで使用されるコンテナーの、機能的な例として、Visual C\+\+ のドキュメントにあります。  詳細については、「[STL コンテナー](../standard-library/stl-containers.md)」を参照してください。  
  
 要素を消去します。  
  
## 構文  
  
```  
  
      iterator erase(  
   iterator _Where   
);  
iterator erase(  
   iterator _First,  
   iterator _Last   
);  
```  
  
## 解説  
 一つ目のメンバー関数は\_Where**.**が指す被制御シーケンスの要素を削除します。2 つ目のメンバー関数は、範囲\[`_First`、`_Last`\) の被制御シーケンスの要素を削除します。  そのような要素が存在しない場合はどちらも、要素を削除した後に残った一つ目の要素を指定する反復子または [終了](../Topic/Container%20Class::end.md)。  
  
 このメンバー関数は、コピー操作が例外をスローする場合に例外をスローします。  
  
## 参照  
 [サンプル コンテナー クラス](../Topic/Sample%20Container%20Class.md)