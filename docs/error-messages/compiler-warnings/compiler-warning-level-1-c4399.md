---
title: "コンパイラの警告 (レベル 1) C4399 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4399
dev_langs:
- C++
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
caps.latest.revision: 9
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
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 7d7584e318a42530a2a91fee4b428c92bfaf120c
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4399"></a>コンパイラの警告 (レベル 1) C4399
'symbol': プロセスごとのシンボルを/clr でのコンパイル時に _declspec (dllimport) と共に設定できません必要があります: 純粋な  
  
 **/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 で使用されなくなりました。  
  
 ネイティブ イメージまたはネイティブ モードと CLR コンストラクトを使用してイメージからのデータを純粋なイメージにインポートすることはできません。 この警告を解決するには、使用してコンパイル**/clr** (いない**/clr: 純粋な**) を削除または`__declspec(dllimport)`です。  
  
## <a name="example"></a>例  
 次の例では、C4399 を生成します。  
  
```  
// C4399.cpp  
// compile with: /clr:pure /doc /W1 /c  
__declspec(dllimport) __declspec(process) extern const int i;   // C4399  
```
