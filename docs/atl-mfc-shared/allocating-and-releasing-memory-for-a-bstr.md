---
title: "BSTR 用のメモリの割り当てと解放 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "bstr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSTRs, メモリの割り当て"
  - "メモリ [C++], 解放"
  - "メモリの割り当て, BSTRs"
  - "メモリ解放, BSTR メモリ"
  - "メモリ解放, 文字列のメモリ"
  - "文字列 [C++], 解放"
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# BSTR 用のメモリの割り当てと解放
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`BSTR`、を作成し、COM オブジェクトの間で渡すと、メモリ リークを回避するために使用するメモリの処理の注意を払う必要があります。  `BSTR` がインターフェイス内に収めると、それにするとメモリを解放する必要があります。  ただし、`BSTR` はインターフェイスを渡すと、受信側のオブジェクトがメモリ管理の必要があります。  
  
 一般に、`BSTR`、のために割り当てるメモリの割り当ておよび解放する規則は次のとおりです。:  
  
-   `BSTR` の引数を受け取る関数を呼び出すときには、呼び出しの前に `BSTR` のメモリを割り当て、その後に解放する必要があります。  以下はその例です。  
  
     [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_1.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_2.cpp)]  
  
-   `BSTR`を返す関数を呼び出すときは、文字列を解放する必要があります。  以下はその例です。  
  
     [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_3.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_4.cpp)]  
  
-   `BSTR`を返す関数を実行すると、文字列を代入しますが、解放しないでください。  関数を受信するとメモリを解放します。  以下はその例です。  
  
     [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_5.cpp)]  
  
## 参照  
 [文字列](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT::AllocSysString](../Topic/CStringT::AllocSysString.md)   
 [SysAllocString](http://msdn.microsoft.com/ja-jp/9e0437a2-9b4a-4576-88b0-5cb9d08ca29b)   
 [SysFreeString](http://msdn.microsoft.com/ja-jp/8f230ee3-5f6e-4cb9-a910-9c90b754dcd3)