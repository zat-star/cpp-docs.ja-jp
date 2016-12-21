---
title: "文字シーケンス | Microsoft Docs"
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
  - "C"
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 文字シーケンス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.8.2** ソース ファイルの文字シーケンスのマッピング  
  
 プリプロセッサ ステートメントは、ソース ファイル ステートメントと同じ文字セットを使用しますが、エスケープ シーケンスはサポートされていません。  
  
 したがって、インクルード ファイルのパスを指定するには、1 つの円記号 \(バックスラッシュ\) のみを使用します。  
  
```  
#include "path1\path2\myfile"  
```  
  
 ソース コード内では、次のように、2 つの円記号 \(バックスラッシュ\) が必要です。  
  
```  
fil = fopen( "path1\\path2\\myfile", "rt" );  
```  
  
## 参照  
 [プリプロセス ディレクティブ](../Topic/Preprocessing%20Directives.md)