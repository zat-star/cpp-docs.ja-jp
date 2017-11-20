---
title: "リンカ ツール エラー LNK2028 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2028
dev_langs: C++
helpviewer_keywords: LNK2028
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 06865e305e8c87d6a3b4bb74b7b1c7dae7cd45a8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2028"></a>リンカ ツール エラー LNK2028
"exported_function"(decorated_name) 関数"function_containing_function_call"(decorated_name) で参照されています。  
  
 ネイティブ関数を純粋なイメージにインポートするは、ネイティブと純粋なコンパイルの間で暗黙の呼び出し規約が異なることに注意してください。  
  
## <a name="example"></a>例  
 このコード サンプルは、ネイティブ、エクスポートされた関数の呼び出し規約は暗黙的に持つコンポーネントを生成[_ _cdecl](../../cpp/cdecl.md)です。  
  
```  
// LNK2028.cpp  
// compile with: /LD  
__declspec(dllexport) int func() {  
   return 3;  
}  
```  
  
## <a name="example"></a>例  
 次の例では、純粋なネイティブ関数を使用するクライアントを作成します。 ただし、下にある呼び出し規約**/clr: 純粋な**は[_ _clrcall](../../cpp/clrcall.md)です。 次の例では、LNK2028 が生成されます。  
  
```  
// LNK2028_b.cpp  
// compile with: /clr:pure lnk2028.lib  
// LNK2028 expected  
int func();  
  
int main() {  
   return func();  
}  
```