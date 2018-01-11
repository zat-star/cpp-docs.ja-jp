---
title: "リンカ ツール エラー LNK1107 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1107
dev_langs: C++
helpviewer_keywords: LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fae412de31163aa1b5248af43227042cd04563ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1107"></a>リンカ ツール エラー LNK1107
ファイルが無効か破損しています: の場所で読み取ることができません  
  
 このツールは、ファイルを読み取れませんでした。 ファイルを再作成します。  
  
 モジュールを渡すしようとする場合にも LNK1107 (で作成された拡張子は .dll または .netmodule [/clr:noAssembly](../../build/reference/clr-common-language-runtime-compilation.md)または[/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)) リンカー; するには、.obj ファイルを代わりに渡します。  
  
 次の例: コンパイルする場合  
  
```  
// LNK1107.cpp  
// compile with: /clr /LD  
public ref class MyClass {  
public:  
   void Test(){}  
};  
```  
  
 指定し、 **LNK1107.dll をリンク**コマンド ラインで LNK1107 が表示されます。  エラーを解決するには、指定**リンク LNK1107.obj**代わりにします。