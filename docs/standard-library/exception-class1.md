---
title: "exception クラス | Microsoft Docs"
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
  - "std.exception"
  - "exception"
  - "std::exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exception クラス"
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# exception クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このクラスは、特定の式と標準 C\+\+ ライブラリによってスローされたすべての例外の基底クラスとして機能します。  
  
## 構文  
  
```  
class exception {  
public:  
    exception();  
    exception(const char * const &message);  
    exception(const char * const &message, int);  
    exception(const exception &right);  
    exception& operator=(const exception &right);  
    virtual ~exception();  
    virtual const char *what() const;  
};  
```  
  
## 解説  
 具体的には、この基本クラスは [\<stdexcept\>](../standard-library/stdexcept.md)で定義されている標準の例外クラスのルートです。  `what` によって返される C の文字列値は、既定のコンストラクターによって、未指定残されましたり、特定の派生クラスのコンストラクターによって実装定義された C の文字列として定義されている場合があります。  メンバー関数では、例外をスローしません。  
  
 `int` パラメーターは、メモリの割り当てしないことを指定することができます。  `int` の値は無視されます。  
  
> [!NOTE]
>  `exception(const char * const &message)` と `exception(const char * const &message, int)` コンストラクターは、標準 C\+\+ ライブラリに Microsoft 拡張機能です。  
  
## 使用例  
 `exception` クラスから継承する標準の例外クラスの使用例については、" [\<stdexcept\>](../standard-library/stdexcept.md)で定義されているクラスを参照してください。  
  
## 必要条件  
 **ヘッダー:** \<例外\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)