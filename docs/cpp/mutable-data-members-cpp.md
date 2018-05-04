---
title: 変更可能なデータ メンバー (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- mutable_cpp
dev_langs:
- C++
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7dd639cbf1ef076dee6e447f317533bf12dae10
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="mutable-data-members-c"></a>変更可能なデータ メンバー (C++)
このキーワードは、クラスの non-static データ メンバーおよび non-const データ メンバーにのみ適用できます。 データ メンバーが宣言されている場合`mutable`からこのデータ メンバーに値を代入することは、 **const**メンバー関数。  
  
## <a name="syntax"></a>構文  
  
```  
  
mutable member-variable-declaration;  
```  
  
## <a name="remarks"></a>コメント  
 たとえば次のコードは、`m_accessCount` が `mutable` として宣言されており、したがって `GetFlag` が const メンバー関数であっても `GetFlag` によって変更できるために、エラーなくコンパイルされます。  
  
```  
// mutable.cpp  
class X  
{  
public:  
   bool GetFlag() const  
   {  
      m_accessCount++;  
      return m_flag;  
   }  
private:  
   bool m_flag;  
   mutable int m_accessCount;  
};  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)