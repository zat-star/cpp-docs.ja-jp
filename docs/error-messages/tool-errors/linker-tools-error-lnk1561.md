---
title: "リンカ ツール エラー LNK1561 | Microsoft Docs"
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
  - "LNK1561"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1561"
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK1561
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

エントリー ポイントを定義する必要があります。  
  
 リンカーによってエントリ ポイントが検出されませんでした。  DLL としてリンクしようとした可能性があります。DLL としてリンクする場合は、[\/DLL](../../build/reference/dll-build-a-dll.md) オプションを使用する必要があります。  エントリ ポイントの名前が指定されていない可能性もあります。その場合は、[\/ENTRY](../../build/reference/entry-entry-point-symbol.md) オプションを使用してリンクします。  
  
 それ以外の場合は、main、wmain、WinMain、wMain の各関数をコードに記述する必要があります。  
  
 [LIB](../../build/reference/lib-reference.md) を使用して .dll をビルドした場合は、このエラーの原因の 1 つとして、.def ファイルを指定したことが考えられます。  その場合は、ビルドから .def ファイルを削除してください。  
  
 次の例では警告 LNK1561 が生成されます。  
  
```  
// LNK1561.cpp  
// LNK1561 expected  
int i;  
// add a main function to resolve this error  
```