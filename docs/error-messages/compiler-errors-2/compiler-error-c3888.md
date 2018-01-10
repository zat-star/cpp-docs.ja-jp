---
title: "コンパイラ エラー C3888 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3888
dev_langs: C++
helpviewer_keywords: C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e6f0310324afcbde112623959c4dc3b11155fed1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3888"></a>コンパイラ エラー C3888
'name': このリテラル データ メンバーと関連付けられた const 式は C++/CLI でサポートされていません  
  
 *literal* キーワードを使用して宣言された [name](../../windows/literal-cpp-component-extensions.md) データ メンバーが、コンパイラがサポートしていない値で初期化されています。 コンパイラは、定数の整数型、列挙型、または文字列型のみをサポートしています。 **C3888** エラーの考えられる原因は、データ メンバーがバイト配列で初期化されていることです。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  宣言されたリテラル データ メンバーがサポートされている型であることを確認します。  
  
## <a name="see-also"></a>参照  
 [name](../../windows/literal-cpp-component-extensions.md)