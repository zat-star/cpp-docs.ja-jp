---
title: "marshal_context クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "marshal_context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_context クラス [C++]"
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# marshal_context クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このクラスには、ネイティブ コードとマネージ環境との間でデータを変換します。  
  
## 構文  
  
```  
class marshal_context  
```  
  
## 解説  
 コンテキストを必要とするデータ変換に `marshal_context` クラスを使用します。  変換がコンテキストを必要とするマーシャリング ファイルが含まれ、詳細については、" [C\+\+ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md) を参照してください。  コンテキストを使用する場合、マーシャリングの結果は `marshal_context` オブジェクトが破棄されるまでのみ有効です。  結果を保持するために、データをコピーする必要があります。  
  
 同じ `marshal_context` は複数のデータ変換に使用できます。  コンテキストを再利用するには、このように前のマーシャリングの呼び出しの結果には影響しません。  
  
## 必要条件  
 **Header file:** \<msclr\\marshal.h、\> \<msclr\\marshal\_windows.h、\> \<msclr\\marshal\_cppstd.h、または\> \<msclr\\marshal\_atl.h\>  
  
 **名前空間:** msclr::interop  
  
## 参照  
 [C\+\+ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_as](../dotnet/marshal-as.md)