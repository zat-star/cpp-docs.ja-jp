---
title: "コンパイラの警告 (レベル 4) C4435 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
caps.latest.revision: 2
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 0d419a4e96ee0716e710b93ce0fa93276ec858aa
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-4-c4435"></a>コンパイラの警告 (レベル 4) C4435
'class1': /vd2 下のオブジェクトのレイアウトは仮想ベース 'class2' により変更されます。  
  
 既定では、この警告はオフに設定されています。 参照してください[コンパイラの警告ことは既定で無効](../../preprocessor/compiler-warnings-that-are-off-by-default.md)の詳細。  
  
 コンパイル/vd1 のオプションを既定値で、派生クラスがない、`vtordisp`示された仮想ベースのフィールドです。  場合/vd2 または`#pragma vtordisp(2)`が有効で、`vtordisp`フィールドは存在し、オブジェクトのレイアウトの変更になります。  異なる処理を行うモジュールがコンパイルされている場合のバイナリ互換性の問題につながります`vtordisp`設定します。  
  
## <a name="example"></a>例  
 次の例では、C4435 を生成します。  
  
```cpp  
// C4435.cpp  
// compile with: /c /W4  
#pragma warning(default : 4435)  
class A  
{  
public:  
    virtual ~A() {}  
};  
  
class B : public virtual A  // C4435  
{};  
```  
  
## <a name="see-also"></a>関連項目  
 [vtordisp](../../preprocessor/vtordisp.md)   
 [/vd (ディスプレイスメントの無効化)](../../build/reference/vd-disable-construction-displacements.md)
