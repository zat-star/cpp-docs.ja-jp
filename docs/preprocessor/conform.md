---
title: "conform | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "conform_CPP"
  - "vc-pragma.conform"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conform プラグマ"
  - "forScope conform プラグマ"
  - "プラグマ, conform"
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# conform
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 固有の仕様**  
  
 [\/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) コンパイラ オプションの実行時の動作を指定します。  
  
## 構文  
  
```  
#pragma conform(name [, show ] [, on | off ] [ [, push | pop ] [, identifier ] ] )  
```  
  
#### パラメーター  
 *name*  
 変更されるコンパイラ オプションの名前を指定します。  有効な *name* は `forScope` のみです。  
  
 **show**  \(省略可能\)  
 *name* の現在の設定 \(true または false\) がコンパイル中に警告メッセージとして表示されます。  たとえば、`#pragma conform(forScope, show)` のようにします。  
  
 on、off \(省略可能\)  
 *name* を **on** に設定すると、[\/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) コンパイラ オプションが有効になります。  既定値は、**off** です。  
  
 **push** \(省略可能\)  
 *name* の現在の値を内部コンパイラ スタックにプッシュします。  *identifier* を指定する場合、スタックにプッシュされる *name* 値として **on** または **off** を指定できます。  たとえば、`#pragma conform(forScope, push, myname, on)` のようにします。  
  
 **pop** \(省略可能\)  
 *name* の値を内部コンパイラ スタックの最上部の値に設定して、スタックをポップします。  ID が **pop** で指定されると、識別子を持つレコードが見つかるまでスタックがポップされ、見つかったレコードもポップされます。スタック上の次のレコードの名前の現在の値が、名前の新しい値になります。  スタック内のレコードにない *identifier* のポップを指定すると、**pop** は無視されます。  
  
 *識別子* \(省略可能\)  
 **push** コマンドまたは **pop** コマンドに含めることができます。  識別子が使用される場合、**on** 指定子または **off** 指定子も使用できます。  
  
## 使用例  
  
```  
// pragma_directive_conform.cpp  
// compile with: /W1  
// C4811 expected  
#pragma conform(forScope, show)  
#pragma conform(forScope, push, x, on)  
#pragma conform(forScope, push, x1, off)  
#pragma conform(forScope, push, x2, off)  
#pragma conform(forScope, push, x3, off)  
#pragma conform(forScope, show)  
#pragma conform(forScope, pop, x1)  
#pragma conform(forScope, show)  
  
int main() {}  
```  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)