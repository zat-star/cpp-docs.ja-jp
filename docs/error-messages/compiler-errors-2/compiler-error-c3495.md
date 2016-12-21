---
title: "コンパイラ エラー C3495 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3495"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3495"
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3495
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': ラムダ キャプチャには自動ストレージ存続期間が指定されている必要があります  
  
 `static` または `extern` とマークされている変数など、自動ストレージ存続期間がない変数をキャプチャすることはできません。  
  
### このエラーを解決するには  
  
-   `static` または `extern` 変数をラムダ式のキャプチャ リストに渡さないでください。  
  
## 使用例  
 次の例では、`static` 変数 `n` がラムダ式のキャプチャ リストにあるため、C3495 が生成されます。  
  
```  
// C3495.cpp int main() { static int n = 66; [&n]() { return n; }(); // C3495 }  
```  
  
## 参照  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)   
 [\(NOTINBUILD\) ストレージ クラス指定子](http://msdn.microsoft.com/ja-jp/10b3d22d-cb40-450b-994b-08cf9a211b6c)