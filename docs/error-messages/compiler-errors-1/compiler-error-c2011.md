---
title: "コンパイラ エラー C2011 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2011
dev_langs:
- C++
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c599d6add1fa51c6aae7f04019eacdc94f11bb15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2011"></a>コンパイラ エラー C2011
'identifier' : 'type' 型の再定義  
  
 この識別子は、既に `type` として定義されています。 識別子の再定義をチェックします。  
  
 ヘッダー ファイルまたはタイプ ライブラリを同じファイルに 2 回以上インポートすると、C2011 が生成される場合もあります。 ヘッダー ファイルで定義された型の複数のインクルードを防ぐためには、使用する #include guard または`#pragma`[したら](../../preprocessor/once.md)ヘッダー ファイルでディレクティブです。  
  
 使用することができますを再定義された型の最初の宣言を検索する必要がある場合、 [/P](../../build/reference/p-preprocess-to-a-file.md)コンパイラに渡されたプリプロセス済みの出力を生成するコンパイラ フラグ。 テキスト検索ツールを使用して、出力ファイル内の再定義された識別子のインスタンスを見つけることができます。  
  
 次の例では、C2011 を生成し、その修正方法を示しています。  
  
```  
// C2011.cpp  
// compile with: /c  
struct S;  
union S;   // C2011  
union S2;   // OK  
```