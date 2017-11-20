---
title: "リンカ ツール エラー LNK1237 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1237
dev_langs: C++
helpviewer_keywords: LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 43ab77f153b6e53709422a1826a6beee25d65b2a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1237"></a>リンカ ツール エラー LNK1237
コード生成中には、コンパイラはシンボル 'symbol' は 'module'/GL でコンパイルされたモジュールで定義されているへの参照を導入しました。  
  
 コード生成中に、コンパイラは、後でコンパイルされた定義を解決するシンボル**/GL**です。 `symbol`導入され、後でコンパイルした定義に解決される記号**/GL**です。  
  
 詳細については、「[/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)」を参照してください。  
  
 LNK1237 を解決するには、コンパイルしないで、シンボルの**/GL**使用または[/INCLUDE (シンボル参照の強制)](../../build/reference/include-force-symbol-references.md)シンボルへの参照を強制的にします。  
  
## <a name="example"></a>例  
 次の例では、LNK1237 が生成されます。 このエラーを解決するのには LNK1237_a.cpp で配列を初期化されず、追加**/include: _chkstk**リンク コマンド。  
  
```  
// LNK1237_a.cpp  
int main() {  
   char c[5000] = {0};  
}  
```  
  
```  
// LNK1237_b.cpp  
// compile with: /GS- /GL /c LNK1237_a.cpp  
// processor: x86  
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)  
extern "C" void _chkstk(size_t s) {}  
```