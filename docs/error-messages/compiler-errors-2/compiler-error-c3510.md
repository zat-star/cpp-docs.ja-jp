---
title: "コンパイラ エラー C3510 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3510
dev_langs:
- C++
helpviewer_keywords:
- C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9603a4f94106d491ea5e14f30b36b1b230554ad2
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3510"></a>コンパイラ エラー C3510
依存タイプ ライブラリ 'type_lib' を見つけることができません。  
  
 [no_registry](../../preprocessor/no-registry.md)と[auto_search](../../preprocessor/auto-search.md)に渡された`#import`が、コンパイラが参照されるタイプ ライブラリを検索することができませんでした。  
  
 このエラーを解決するには、すべてのタイプ ライブラリおよび参照タイプ ライブラリがコンパイラに利用できることを確認します。  
  
 次の例では、C3510 が生成されます。  
  
 します。 次の 2 つのタイプ ライブラリがビルドされた C3510a.tlb が削除されたか、パスではなくです。  
  
```  
// C3510a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library C3510aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C3510  
   {  
      one, two, three  
   };  
};  
```  
  
 ソース コードの 2 つ目のタイプ ライブラリ:  
  
```  
// C3510b.idl  
// post-build command: del /f C3510a.tlb  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
library C3510bLib  
{  
   importlib ("C3510a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
   struct S_C3510 {  
      enum E_C3510 e;  
   };  
};  
```  
  
 クライアント コード:  
  
```  
// C3510.cpp  
#import "c3510b.tlb" no_registry auto_search   // C3510  
int main() {  
   C3510aLib::S_C4336 ccc;  
}  
```
