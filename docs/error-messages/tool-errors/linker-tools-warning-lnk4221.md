---
title: "リンカー ツールの警告 LNK4221 | Microsoft Docs"
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
  - "LNK4221"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4221"
ms.assetid: 8e2eb2de-9532-4b85-908a-8c9ff5c4cccb
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー ツールの警告 LNK4221
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このオブジェクト ファイルは、以前に未定義であったパブリック シンボルを定義していないため、このライブラリを使用するリンク操作では使用されません  
  
 次の 2 つのコード スニペットについて考えます。  
  
```  
// a.cpp  
#include <atlbase.h>  
```  
  
```  
// b.cpp  
#include <atlbase.h>  
int function()  
{  
   return 0;  
}  
  
```  
  
 ファイルをコンパイルし 2 つのオブジェクト ファイルを作成するには、コマンド プロンプトで **cl \/c a.cpp b.cpp** を実行します。  **link \/lib \/out:test.lib a.obj b.obj** を実行してオブジェクト ファイルをリンクすると、LNK4221 警告が表示されます。  **link \/lib \/out:test.lib b.obj a.obj** を実行してオブジェクトをリンクすると、警告は表示されません。  
  
 後入れ先出し \(LIFO\) 方式でリンカーは動作するため、2 番目のシナリオでは警告メッセージは表示されません。  1 番目のシナリオでは、a.obj の前に b.obj が処理され、a.obj には追加する新しいシンボルがありません。  a.obj を最初に処理するようリンカーに指示することで、警告が表示されないようにすることができます。  
  
 このエラーが一般的に発生するのは、2 つのソース ファイルがオプション [\/Yc \(プリコンパイル済みヘッダー ファイルの作成\)](../../build/reference/yc-create-precompiled-header-file.md) を指定し、**\[プリコンパイル済みヘッダー\]** フィールドで同じヘッダー ファイル名が指定された場合です。  既定では、stdafx.cpp には stdafx.h が含まれ、新しいシンボルは追加されないため、通常この問題が発生すると、stdafx.h が処理されます。  別のソース ファイルに、stdafx.h と **\/Yc** が含まれ、関連付けられている .obj ファイルが stdafx.obj の前に処理される場合、リンカーは LNK4221 をスローします。  
  
 この問題を解決する 1 つの方法は、プリコンパイル済みヘッダーごとに、**\/Yc** を含むソース ファイルが 1 つだけ存在することを確認することです。  他のすべてのソース ファイルは、プリコンパイル済みヘッダーを使用する必要があります。  この設定の変更方法の詳細については、「[\/Yu \(プリコンパイル済みヘッダー ファイルの使用\)](../../build/reference/yu-use-precompiled-header-file.md)」を参照してください。