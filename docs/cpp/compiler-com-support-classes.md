---
title: "コンパイラ COM サポート クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_raise_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe コンパイラ, COM サポート"
  - "COM, コンパイラ サポート"
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# コンパイラ COM サポート クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 標準クラスは、COM 型の一部をサポートするために使用されます。  クラスは、comdef.h ファイル、およびタイプ ライブラリから生成されたヘッダー ファイルで定義されます。  
  
|クラス|目的|  
|---------|--------|  
|[\_bstr\_t](../cpp/bstr-t-class.md)|便利な演算子とメソッドを提供するために、`BSTR` 型をラップします。|  
|[\_com\_error](../cpp/com-error-class.md)|ほとんどのエラーで [\_com\_raise\_error](../cpp/com-raise-error.md) によってスローされるエラー オブジェクトを定義します。|  
|[\_com\_ptr\_t](../cpp/com-ptr-t-class.md)|COM インターフェイス ポインターをカプセル化し、`AddRef`、**Release**、および `QueryInterface` への必要な呼び出しを自動化します。|  
|[\_variant\_t](../cpp/variant-t-class.md)|便利な演算子とメソッドを提供するために、**VARIANT** 型をラップします。|  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [コンパイラ COM サポート](../Topic/Compiler%20COM%20Support.md)   
 [コンパイラ COM のグローバル関数](../cpp/compiler-com-global-functions.md)   
 [C\+\+ 言語リファレンス](../cpp/cpp-language-reference.md)