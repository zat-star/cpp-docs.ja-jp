---
title: "コンパイラ エラー C3468 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3468
dev_langs: C++
helpviewer_keywords: C3468
ms.assetid: cfd320db-2f6e-4e0d-ba02-e79ece87e1e0
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 41fde9cae4697c38dba410fb1fbdb46cd901ae97
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3468"></a>コンパイラ エラー C3468
'type': 型は次のアセンブリにのみ転送できます:  
  
 '`file`' はアセンブリではありません  
  
 アセンブリ内の型のみを転送することができます。  
  
 詳細については、次を参照してください。 [Type Forwarding (C + + CLI)](../../windows/type-forwarding-cpp-cli.md)です。  
  
## <a name="example"></a>例  
 モジュールを作成する例を次に示します。  
  
```  
// C3468.cpp  
// compile with: /LN /clr  
public ref class R {};  
```  
  
## <a name="example"></a>例  
 次の例では C3468 が生成されます。  
  
```  
// C3468_b.cpp  
// compile with: /clr /c  
#using "C3468.netmodule"  
[ assembly:TypeForwardedTo(R::typeid) ];   // C3468  
```