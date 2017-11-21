---
title: "コンパイラの警告 (レベル 1) C4377 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4377
dev_langs: C++
helpviewer_keywords: C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e52479aac07cdb31f62b20cb6c865b48b270c2bb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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