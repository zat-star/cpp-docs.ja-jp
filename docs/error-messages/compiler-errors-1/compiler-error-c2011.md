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
caps.latest.revision: 10
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: ed0aa8e9db0829716765128c9d409de9852808e1
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2011"></a>コンパイラ エラー C2011
'identifier' : 'type' 型の再定義  
  
 この識別子は、既に `type` として定義されています。 識別子の再定義をチェックします。  
  
 ヘッダー ファイルまたはタイプ ライブラリを同じファイルに&2; 回以上インポートすると、C2011 が生成される場合もあります。 ヘッダー ファイルで定義された型の多重インクルードを防ぐためには、使用にガードが含まれている、または`#pragma`[したら](../../preprocessor/once.md)ヘッダー ファイルにディレクティブです。  
  
 使用することができますを再定義された型の最初の宣言を検索する必要がある場合、 [/P](../../build/reference/p-preprocess-to-a-file.md)プリプロセス済みの出力を生成するコンパイラ フラグをコンパイラに渡します。 テキスト検索ツールを使用して、出力ファイル内の再定義された識別子のインスタンスを見つけることができます。  
  
 次の例では、C2011 を生成し、その修正方法を示しています。  
  
```  
// C2011.cpp  
// compile with: /c  
struct S;  
union S;   // C2011  
union S2;   // OK  
```
