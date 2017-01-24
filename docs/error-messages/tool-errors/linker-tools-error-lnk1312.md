---
title: "リンカ ツール エラー LNK1312 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1312"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1312"
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK1312
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルが無効であるか､ または壊れています: アセンブリをインポートできません。  
  
 アセンブリのビルド時に、**\/clr** でコンパイルされたモジュールまたはアセンブリ以外のファイルが **\/ASSEMBLYMODULE** リンカー オプションに渡されました。オブジェクト ファイルを **\/ASSEMBLYMODULE** に渡す場合は、オブジェクトを **\/ASSEMBLYMODULE** にではなく、リンカーに直接渡します。  
  
## 使用例  
 次のサンプルでは .obj ファイルが作成されます。  
  
```  
// LNK1312.cpp  
// compile with: /clr /LD  
public ref class A {  
public:  
   int i;  
};  
```  
  
## 使用例  
 次の例では LNK1312 エラーが生成されます。  
  
```  
// LNK1312_b.cpp  
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj  
// LNK1312 error expected  
public ref class M {};  
```