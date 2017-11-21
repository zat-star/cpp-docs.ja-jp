---
title: "コンパイラ エラー C3836 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3836
dev_langs: C++
helpviewer_keywords: C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 43f7972efc5e8b930811817f5cef9c415a60cb5d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3836"></a>コンパイラ エラー C3836
静的コンス トラクターはメンバー初期化子リストを取得できません。  
  
 マネージ クラスには、静的コンス トラクターを持つメンバー初期化リストを持つことはできません。 クラスの初期化、静的データ メンバーの初期化を実行する共通言語ランタイムによっては、静的クラス コンス トラクターが呼び出されます。  
  
## <a name="example"></a>例  
 次の例では、C3836 が生成されます。  
  
```  
// C3836a.cpp  
// compile with: /clr  
ref class M  
{  
   static int s_i;  
  
public:  
   static M() :  s_i(1234)   // C3836, delete initializer to resolve  
   {  
   }  
};  
  
int main()  
{  
}  
```  
