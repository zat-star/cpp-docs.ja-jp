---
title: "変更可能なデータ メンバー (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: mutable_cpp
dev_langs: C++
helpviewer_keywords: mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a3c960c5fcf5a73d339b7565cd0bec38dba98f12
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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