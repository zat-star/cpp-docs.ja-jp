---
title: "遅延読み込みする DLL の指定 | Microsoft Docs"
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
helpviewer_keywords: 
  - "/DELAYLOAD リンカー オプション"
  - "遅延読み込み (DLL を)"
  - "遅延読み込み (DLL を), 指定"
  - "DELAYLOAD リンカー オプション"
ms.assetid: 94cbecfe-7a42-40d1-a618-9f2786bac0d8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 遅延読み込みする DLL の指定
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/delayload](../../build/reference/delayload-delay-load-import.md):`dllname` リンカー オプションを使用して、遅延読み込みする DLL を指定できます。  独自のバージョンのヘルパー関数を使う計画がない場合は、プログラムを delayimp.lib \(デスクトップ アプリケーションの場合\) または dloadhelper.lib \(ストア アプリの場合\) とリンクする必要もあります。  
  
 DLL の遅延読み込みの簡単な例を以下に示します。  
  
```  
// cl t.cpp user32.lib delayimp.lib  /link /DELAYLOAD:user32.dll  
#include <windows.h>  
// uncomment these lines to remove .libs from command line  
// #pragma comment(lib, "delayimp")  
// #pragma comment(lib, "user32")  
  
int main() {  
   // user32.dll will load at this point  
   MessageBox(NULL, "Hello", "Hello", MB_OK);  
}  
```  
  
 DEBUG バージョンのプロジェクトをビルドします。  デバッガーを使ってコードを段階的に実行すると、`MessageBox` に対する呼び出しを行なう場合のみ user32.dll が読み込まれることがわかります。  
  
## 参照  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)