---
title: "リンカ ツール エラー LNK2031 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2031
dev_langs: C++
helpviewer_keywords: LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8732b9deaf1da2e27b8f95aed63d09e9f4c41dec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2031"></a>リンカ ツール エラー LNK2031
"function_declaration"decorated_name; の p/invoke を生成できません。呼び出し規約がメタデータに見つかりません。  
  
 ネイティブ関数を純粋なイメージにインポートするは、ネイティブと純粋なコンパイルの間で暗黙の呼び出し規約が異なることに注意してください。 純粋なイメージの詳細については、次を参照してください。[純粋なコードと検証可能なコード (C + + CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)です。  
  
## <a name="example"></a>例  
 このコード サンプルは、ネイティブ、エクスポートされた関数の呼び出し規約は暗黙的に持つコンポーネントを生成[_ _cdecl](../../cpp/cdecl.md)です。  
  
```  
// LNK2031.cpp  
// compile with: /LD  
extern "C" {  
   __declspec(dllexport) int func() { return 3; }  
};  
```  
  
## <a name="example"></a>例  
 次の例では、純粋なネイティブ関数を使用するクライアントを作成します。 ただし、下にある呼び出し規約**/clr: 純粋な**は[_ _clrcall](../../cpp/clrcall.md)です。 次の例では、LNK2031 が生成されます。  
  
```  
// LNK2031_b.cpp  
// compile with: /clr:pure LNK2031.lib  
// LNK2031 expected  
extern "C" int func();  
  
int main() {  
   return func();  
}  
```  
  
## <a name="example"></a>例  
 次の例では、純粋なイメージからネイティブ関数を使用する方法を示します。 明示的に注意してください**_ _cdecl**呼び出し規約の指定子。  
  
```  
// LNK2031_c.cpp  
// compile with: /clr:pure LNK2031.lib  
extern "C" int __cdecl func();  
  
int main() {  
   return func();  
}  
```