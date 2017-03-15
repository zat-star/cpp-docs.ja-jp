---
title: "コンパイラの警告 (レベル 1) C4067 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4067"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4067"
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 1) C4067
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プリプロセッサ ディレクティブの後に余分な文字がありました \- 改行が必要です  
  
 プリプロセッサ ディレクティブの後ろに余分な文字がありましたが、無視されました。  この警告が表示されるのは、ANSI 互換のオプション \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) を指定した場合だけです。  
  
```  
// C4067a.cpp  
// compile with: /DX /Za /W1  
#pragma warning(default:4067)  
#if defined(X)  
#else  
#endif v   // C4067  
int main()  
{  
}  
```  
  
### この警告を解決するには:  
  
1.  **\/Ze** を指定してコンパイルします。  
  
2.  次のように、コメント デリミターを使用します。  
  
```  
// C4067b.cpp  
// compile with: /DX /Za /W1  
#if defined(X)  
#else  
#endif  
int main()  
{  
}  
```