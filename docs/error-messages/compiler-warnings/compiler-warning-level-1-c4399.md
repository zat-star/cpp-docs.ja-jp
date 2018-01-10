---
title: "コンパイラの警告 (レベル 1) C4399 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4399
dev_langs: C++
helpviewer_keywords: C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eff01c29d423b0823b41bf63702cf42ee839a523
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4399"></a>コンパイラの警告 (レベル 1) C4399
'symbol': プロセスごとのシンボルは/clr でコンパイルされるときにマークしないで: 純粋な  
  
 **/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 で推奨されなくなりました。  
  
 ネイティブ イメージまたはネイティブ モードと CLR コンストラクトを使用してイメージからのデータを純粋なイメージにインポートすることはできません。 この警告を解決するには、コンパイル時に**/clr** (いない**/clr: 純粋な**) を削除または`__declspec(dllimport)`です。  
  
## <a name="example"></a>例  
 次の例では、C4399 を生成します。  
  
```  
// C4399.cpp  
// compile with: /clr:pure /doc /W1 /c  
__declspec(dllimport) __declspec(process) extern const int i;   // C4399  
```