---
title: "コンパイラの警告 (レベル 1) C4269 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4269
dev_langs: C++
helpviewer_keywords: C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ee524e998a4d314b7ae3fff74b48b8a6ca6a621f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4269"></a>コンパイラの警告 (レベル 1) C4269
'identifier': 'const' で自動データ初期化コンパイラによって生成された既定のコンス トラクターには、信頼性のない結果が生成されます  
  
 A **const**コンパイラによって生成された既定のコンス トラクターを持つ重要なクラスの自動インスタンスを初期化します。  
  
## <a name="example"></a>例  
  
```  
// C4269.cpp  
// compile with: /c /LD /W1  
class X {  
public:  
   int m_data;  
};  
  
void g() {  
   const X x1;   // C4269  
};  
```  
  
 クラスのこのインスタンスは、スタックの初期値に生成されてから`m_data`何でもかまいません。 また、以降は、 **const**の値をインスタンス`m_data`は変更不可能です。