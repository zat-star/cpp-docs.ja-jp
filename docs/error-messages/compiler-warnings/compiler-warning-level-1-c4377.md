---
title: "コンパイラの警告 (レベル 1) C4377 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4377
dev_langs:
- C++
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b2cf61aa35bcfc40a40febb9e066caba6decd682
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4377"></a>コンパイラの警告 (レベル 1) C4377
ネイティブ型は、既定でプライベート--d1privatenativetypes は使用できません  
  
 以前のリリースではアセンブリのネイティブ型がパブリックで、既定値、および内部のドキュメントに未記載のコンパイラ オプション (**/d1PrivateNativeTypes**) がプライベートにするために使用します。  
  
 ネイティブに、すべての型と CLR、プライベート アセンブリでは、既定では、今すぐように**/d1PrivateNativeTypes**は不要です。  
  
## <a name="example"></a>例  
 次の例では、C4377 を生成します。  
  
```  
// C4377.cpp  
// compile with: /clr /d1PrivateNativeTypes /W1  
// C4377 warning expected  
int main() {}  
```