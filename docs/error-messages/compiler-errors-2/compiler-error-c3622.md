---
title: "コンパイラ エラー C3622 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3622
dev_langs: C++
helpviewer_keywords: C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a5ebccc9fb6cc8c25a8a6b42ae3b99439b1f5d44
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3622"></a>コンパイラ エラー C3622
'class': 宣言されたクラスを 'keyword' をインスタンス化することはできません  
  
としてマークされたクラスのインスタンスを作成しようとしました[抽象](../../windows/abstract-cpp-component-extensions.md)です。 としてマークされているクラス`abstract`基底クラスを指定できますが、インスタンス化することはできません。  
  
## <a name="example"></a>例  
次の例では、C3622 を生成します。  
  
```  
// C3622.cpp  
// compile with: /clr  
ref class a abstract {};  
  
int main() {  
   a aa;   // C3622  
}  
```  
