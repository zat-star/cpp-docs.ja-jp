---
title: "コンパイラの警告 (レベル 1) C4742 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4742
dev_langs: C++
helpviewer_keywords: C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: da12d4d1e5e8b6f9be6c21601e04f08d1b269cec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4742"></a>コンパイラの警告 (レベル 1) C4742
'var' が 'file1' および 'file2' 内で異なるアラインメント: 番号と番号  
  
 参照または 2 つのファイルで定義されている外部変数は、それらのファイルで異なるアラインメントをいます。 コンパイラを検索するときに、この警告が生成されます`__alignof`で変数の*file1*異なる`__alignof`で変数の*file2*です。 可能性があります、別のファイル内の変数を宣言するときに、互換性のない型を使用して、または一致しないを使用して`#pragma pack`別のファイルにします。  
  
 この警告を解決するのには、同じ種類の定義を使用するか、または異なる名前の変数を使用します。  
  
 詳細については、次を参照してください。[パック](../../preprocessor/pack.md)と[_ _alignof 演算子](../../cpp/alignof-operator.md)です。  
  
## <a name="example"></a>例  
 これは、型を定義する最初のファイルです。  
  
```  
// C4742a.c  
// compile with: /c  
struct X {  
   char x, y, z, w;  
} global;  
```  
  
## <a name="example"></a>例  
 次の例では、C4742 を生成します。  
  
```  
// C4742b.c  
// compile with: C4742a.c /W1 /GL  
// C4742 expected  
extern struct X {  
   int a;  
} global;  
  
int main() {  
   global.a = 0;  
}  
```