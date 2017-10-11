---
title: "コンパイラ エラー C3888 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3888
dev_langs:
- C++
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 26e55c8a675ada3fd2e88976bc9d9a51cfa8b751
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3888"></a>コンパイラ エラー C3888
'name': このリテラル データ メンバーと関連付けられた const 式は C++/CLI でサポートされていません  
  
 *literal* キーワードを使用して宣言された [name](../../windows/literal-cpp-component-extensions.md) データ メンバーが、コンパイラがサポートしていない値で初期化されています。 コンパイラは、定数の整数型、列挙型、または文字列型のみをサポートしています。 **C3888** エラーの考えられる原因は、データ メンバーがバイト配列で初期化されていることです。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  宣言されたリテラル データ メンバーがサポートされている型であることを確認します。  
  
## <a name="see-also"></a>関連項目  
 [name](../../windows/literal-cpp-component-extensions.md)
