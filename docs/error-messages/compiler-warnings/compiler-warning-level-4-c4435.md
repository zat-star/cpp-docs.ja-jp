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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7136cfb61a7452b7e835030216d08f064874df8b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4435"></a>コンパイラの警告 (レベル 4) C4435
'class1': /vd2 下のオブジェクトのレイアウトは仮想ベース 'class2' により変更されます。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。  
  
 コンパイル/vd1 のオプションを既定値で、派生クラスがない、`vtordisp`示された仮想ベースのフィールドです。  場合/vd2 または`#pragma vtordisp(2)`が有効で、`vtordisp`フィールドは存在し、オブジェクトのレイアウトの変更になります。  これが問題につながるバイナリの互換性でさまざまな相互作用するモジュールがコンパイルされる場合`vtordisp`設定します。  
  
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
  
## <a name="see-also"></a>参照  
 [vtordisp](../../preprocessor/vtordisp.md)   
 [/vd (ディスプレイスメントの無効化)](../../build/reference/vd-disable-construction-displacements.md)