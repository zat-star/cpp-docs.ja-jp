---
title: 変更可能なデータ メンバー (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- mutable_cpp
dev_langs:
- C++
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a93ae14e6f630d8974163ce8295626a524b49e3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="see-also"></a>参照  
 [キーワード](../cpp/keywords-cpp.md)