---
title: "コンパイラ エラー C3813 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3813"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3813"
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C3813
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロパティ宣言はマネージ型または WinRT 型の定義内でのみ使用できます  
  
 [property](../../misc/property.md) を宣言できるのは、マネージ型または Windows ランタイム型の中でのみです。  ネイティブ型では、`property` キーワードがサポートされていません。  
  
 次の例では、C3813 を生成し、その修正方法を示しています。  
  
```  
// C3813.cpp  
// compile by using: cl /c /clr C3813.cpp  
class A  
{  
   property int Int; // C3813  
};  
  
ref class B  
{  
   property int Int; // OK - declared within managed type  
};  
```