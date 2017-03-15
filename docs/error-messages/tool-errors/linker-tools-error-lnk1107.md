---
title: "リンカ ツール エラー LNK1107 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1107"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1107"
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# リンカ ツール エラー LNK1107
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルが無効であるか、または壊れています : location を読み取れません。  
  
 ファイルを読み込むことができません。  ファイルを作成し直してください。  
  
 LNK1107 は、リンカーへのモジュール \([\/clr: noAssembly](../../build/reference/clr-common-language-runtime-compilation.md) または [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)で作成された .dll または .netmodule 拡張機能\) を渡す場合も発生する可能性があります。; .obj ファイルを渡します。  
  
 次の例をコンパイルします。  
  
```  
// LNK1107.cpp  
// compile with: /clr /LD  
public ref class MyClass {  
public:  
   void Test(){}  
};  
```  
  
 次に、コマンド ラインで **link LNK1107.dll** を指定します。これで、LNK1107 が発生します。このエラーを解決するには、代わりに **link LNK1107.obj** を指定してください。