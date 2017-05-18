---
title: "コンパイラ エラー C3297 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3297
dev_langs:
- C++
helpviewer_keywords:
- C3297
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: dcdcee9235e0007c4d7a6d662b455d98a1cb55da
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3297"></a>コンパイラ エラー C3297
'constraint_2':  'constraint_1' に値の制約があるために、'constraint_1' は制約として使用できません  
  
 値クラスがシールされています。 制約が値クラスの場合は、別の制約はそこから派生できません。  
  
 詳細については、次を参照してください。[ジェネリック型パラメーターの制約 (C + +/CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)します。  
  
## <a name="example"></a>例  
 次の例では C3297 が生成されます。  
  
```  
// C3297.cpp  
// compile with: /clr /c  
generic<class T, class U>  
where T : value class  
where U : T   // C3297  
public ref struct R {};  
```
