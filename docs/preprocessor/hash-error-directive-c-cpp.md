---
title: "#error ディレクティブ (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#error"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#error ディレクティブ"
  - "error ディレクティブ (#error ディレクティブ)"
  - "プリプロセッサ, ディレクティブ"
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #error ディレクティブ (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`#error` ディレクティブは、コンパイル時にユーザー指定のエラー メッセージを出力して、コンパイルを終了します。  
  
## 構文  
  
```  
#error token-string  
```  
  
## 解説  
 このディレクティブが生成するエラー メッセージには、*token\-string* パラメーターが含まれます。  `token-string` パラメーターは、マクロ展開の対象になりません。  このディレクティブは、プリプロセス時にプログラムの不整合や制約の違反を開発者に通知するために最も役立ちます。  次の例は、プリプロセス中のエラーの処理を示しています。  
  
```  
#if !defined(__cplusplus)  
#error C++ compiler required.  
#endif  
```  
  
## 参照  
 [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)