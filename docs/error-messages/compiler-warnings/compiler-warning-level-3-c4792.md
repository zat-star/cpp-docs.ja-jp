---
title: "コンパイラの警告 (レベル 3) C4792 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4792"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4792"
ms.assetid: c047ce69-a622-44e1-9425-d41aa9261c61
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラの警告 (レベル 3) C4792
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

sysimport を使用して関数 'function' が宣言され、ネイティブ コードから参照されました。インポート ライブラリはリンクする必要があります  
  
 DllImport を使用してプログラムにインポートされたネイティブ関数が、アンマネージ関数から呼び出されました。 そのため、DLL のインポート ライブラリにリンクする必要があります。  
  
 コード内、またはコンパイル方法の変更でこの警告を解決することはできません。 この警告を無効にするには、[warning](../../preprocessor/warning.md) プラグマを使用します。  
  
 次の例では C4792 が生成されます。  
  
```  
// C4792.cpp // compile with: /clr /W3 // C4792 expected using namespace System::Runtime::InteropServices; [DllImport("msvcrt")] extern "C" int __cdecl puts(const char *); int main() {} // Uncomment the following line to resolve. // #pragma warning(disable : 4792) #pragma unmanaged void func(void){ puts("test"); }  
```