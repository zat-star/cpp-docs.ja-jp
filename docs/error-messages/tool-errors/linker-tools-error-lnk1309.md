---
title: "リンカ ツール エラー LNK1309 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1309"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1309"
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# リンカ ツール エラー LNK1309
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

type1' モジュールが検出されました。スイッチ \/CLRIMAGETYPE:'type2' では無効です。  
  
 CLR イメージ型が **\/CLRIMAGETYPE** で要求されましたが、1 つ以上のモジュールがその型と互換性がないため、リンカーは要求された型のイメージを生成できませんでした。  
  
 たとえば、**\/CLRIMAGETYPE:safe** を指定し、**\/clr:pure** で作成されたモジュールを渡すと、LNK1309 エラーが発生します。  
  
 また、LNK1309 エラーは、部分的に信頼された CLR 純粋アプリケーションを ptrustu\[d\].lib を使用してビルドする場合にも発生します。  部分的に信頼されたアプリケーションの作成方法については、「[方法: CRT ライブラリ DLL との依存関係を削除して部分信頼アプリケーションを作成する](../../dotnet/create-a-partially-trusted-application.md)」を参照してください。  
  
 詳細については、「[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)」および「[\/CLRIMAGETYPE \(CLR イメージのタイプの指定\)](../Topic/-CLRIMAGETYPE%20\(Specify%20Type%20of%20CLR%20Image\).md)」を参照してください。