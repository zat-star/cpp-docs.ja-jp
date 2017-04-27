---
title: "リンカ ツール エラー LNK1561 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1561
dev_langs:
- C++
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: fbc63a58cd4e276aa2a3f77baeea07d1912eda98
ms.lasthandoff: 04/24/2017

---
# <a name="linker-tools-error-lnk1561"></a>リンカ ツール エラー LNK1561
エントリー ポイントを定義しなければなりません。  
  
リンカーは、エントリ ポイントを見つけられませんでした。 このエラーは、いくつかの原因を持つことができます。  
-   リンクするファイルの一覧で、エントリ ポイントを定義するファイルが含まれていない可能性があります。 エントリ ポイント関数を格納しているファイルがアプリにリンクされていることを確認します。  
-   間違った関数のシグネチャ; を使用して、エントリ ポイントを定義した可能性があります。たとえば、する可能性がありますがスペルが間違っているまたは関数名が大文字を使用または正しく指定されていない戻り値の型またはパラメーターの型。 既定では、リンカー検索、`main`または`wmain`コンソール アプリの関数、`WinMain`または`wWinMain`for Windows アプリでは、関数または`DllMain`dll の初期化が必要です。  
-   指定していない、 [/DLL](../../build/reference/dll-build-a-dll.md) DLL のビルド オプションを選択します。  
-   場合がありますが正しく指定されていないエントリ ポイント関数の名前を使用した場合、 [/ENTRY](../../build/reference/entry-entry-point-symbol.md)リンカー オプション。  
-   使用している場合、 [LIB](../../build/reference/lib-reference.md) DLL をビルドするツール、.def ファイルを指定した可能性があります。 場合は、ビルドから、.def ファイルを削除します。    
  
アプリをビルドする場合、リンカー検索、*エントリ ポイント*コードを開始する、関数が呼び出されます。 これは、アプリが読み込まれ、ランタイムを初期化後に呼び出される関数です。 アプリケーションのためのエントリ ポイント関数を指定する必要がありますか、アプリを実行できません。 エントリ ポイントは、DLL のオプションです。 既定では、リンカー検索など、いくつかの特定の名前とシグネチャのいずれかのエントリ ポイント関数`int main(int, char**)`です。 エントリとして別の関数名を指定できます/ENTRY リンカー オプションを使用してポイント。  
  
## <a name="example"></a>例  
 次の例では、LNK1561 が生成されます。  
  
```cpp  
// LNK1561.cpp  
// LNK1561 expected  
int i;  
// add a main function to resolve this error  
```
