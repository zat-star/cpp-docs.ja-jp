---
title: "リンカー ツールの警告 LNK4254 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4254
dev_langs:
- C++
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e17bcd03f92114c1b7cd21e63220cf6372c17bf2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4254"></a>リンカー ツールの警告 LNK4254
セクション '「section1」' (オフセット) が 'セクション 2' にマージ異なる属性を持つ (オフセット)  
  
 1 つのセクションの内容は、別にマージされたが、2 つのセクションの属性が異なります。 プログラムには、予期しない結果が得られます可能性があります。 たとえば、読み取るしたいデータのみようになりましたがあります書き込み可能なセクションで。  
  
 LNK4254 を解決するには、変更またはマージ要求を削除します。  
  
 X86 を対象とするときにマシンと、C++ での Windows CE ターゲット (ARM、MIPS、SH4、および Thumb)、します。CRT のセクションでは、読み取り専用です。 コードが以前の動作に依存する場合 (です。CRT のセクションでは、読み取り/書き込み)、予期しない現象が発生する可能性があります。  
  
 詳細については、次のトピックを参照してください。  
  
-   [/MERGE (セクション)](../../build/reference/merge-combine-sections.md)  
  
-   [コメント (C/C++)](../../preprocessor/comment-c-cpp.md)  
  
## <a name="example"></a>例  
 次の例では、LNK4254 が生成されます。  
  
```  
// LNK4254.cpp  
// compile with: /W1 /link /WX  
// LNK4254 expected  
#pragma comment(linker, "/merge:.data=.text")  
int main() {}  
```