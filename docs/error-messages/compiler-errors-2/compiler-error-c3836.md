---
title: "コンパイラ エラー C3836 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3836
dev_langs:
- C++
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ed48f6fd044ccc17dacd79d774f8db2c6888a0cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
