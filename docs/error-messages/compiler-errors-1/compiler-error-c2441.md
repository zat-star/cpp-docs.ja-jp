---
title: "コンパイラ エラー C2441 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2441
dev_langs:
- C++
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
caps.latest.revision: 6
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
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 1b98c85df0db4e947ceb5722715f5d020e1ecbec
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2441"></a>コンパイラ エラー C2441
'variable': __declspec(process) で宣言されたシンボルは、const (/clr の) である必要があります: 純粋なモード  
  
 **/Clr: 純粋な**と**/clr:safe**コンパイラ オプションは、Visual Studio 2015 で廃止されました。  
  
 既定では、変数は、アプリケーション ドメインごと**/clr: 純粋な**です。 設定されている、変数`__declspec(process)` **/clr: 純粋な**が&1; つのアプリケーション ドメインに変更し、別の読み取り場合に発生したエラーを生じやすくなります。  
  
 コンパイラが&1; つの変数であるプロセスはそのため、 `const`  **/clr: 純粋な**、すべてのアプリケーション ドメインでのみ読み取りに作成します。  
  
 詳細については、次を参照してください。[プロセス](../../cpp/process.md)と[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)します。  
  
## <a name="example"></a>例  
 次の例では、c2441 エラーを生成します。  
  
```  
// C2441.cpp  
// compile with: /clr:pure /c  
__declspec(process) int i;   // C2441  
__declspec(process) const int j = 0;   // OK  
```
