---
title: "adapter (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "<cliext/adapter>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<adapter> ヘッダー [STL/CLR]"
  - "<cliext/adapter> ヘッダー [STL/CLR]"
  - "アダプター [STL/CLR]"
ms.assetid: 71ce7e51-42b6-4f70-9595-303791a97677
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# adapter (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

STL\/CLR のヘッダー `<cliext/adapter>` は 2 種類のテンプレート クラス \(`collection_adapter` と `range_adapter`\)、およびテンプレート関数 `make_collection`を指定します。  
  
## 構文  
  
```  
#include <cliext/adapter>  
```  
  
## 解説  
  
|\[クラス\]|説明|  
|-------------|--------|  
|[collection\_adapter](../Topic/collection_adapter%20\(STL-CLR\).md)|範囲として Base Class Library \(BCL\) のコレクションをラップします。|  
|[range\_adapter](../dotnet/range-adapter-stl-clr.md)|Optimizing のコレクションとして範囲をラップします。|  
  
|関数|説明|  
|--------|--------|  
|[make\_collection](../dotnet/make-collection-stl-clr.md)|反復子のペアを使用して範囲のアダプターを作成します。|  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/アダプター\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [STL\/CLR ライブラリ](../dotnet/stl-clr-library-reference.md)