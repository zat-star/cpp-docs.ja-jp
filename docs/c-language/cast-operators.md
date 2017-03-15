---
title: "キャスト演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "キャスト演算子"
  - "演算子 [C++], cast"
  - "型キャスト, 演算子"
  - "型変換, キャスト演算子"
ms.assetid: 43b90bbd-39ef-43e6-ae5d-e8a67a01de40
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# キャスト演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型キャストは、特定の状況におけるオブジェクトの型の明示的な変換方法を示します。  
  
## 構文  
 *cast\-expression*:  
 *unary\-expression*  
  
 **\(**  *type\-name*  **\)**  *cast\-expression*  
  
 コンパイラは、型キャストが実行された後で、*cast\-expression* を *type\-name* 型として処理します。  キャストを使用すると、スカラー型オブジェクトの型を他のスカラー型との間で変換できます。  明示的な型キャストは、暗黙的な変換の結果が決定されるときと同じ規則により制限されます。これについては、「[Assignment Conversions \(代入変換\)](../c-language/assignment-conversions.md)」で説明しています。  特定の型の実際のサイズまたは表現から、キャストにさらに制限が課せられる場合があります。  整数型の実際のサイズについては、「[基本型のストレージ](../c-language/storage-of-basic-types.md)」を参照してください。  型キャストの詳細については、「[Type\-Cast Conversions \(型キャスト変換\)](../c-language/type-cast-conversions.md)」を参照してください。  
  
## 参照  
 [キャスト演算子: \(\)](../Topic/Cast%20Operator:%20\(\).md)