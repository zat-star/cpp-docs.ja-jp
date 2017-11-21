---
title: "コンパイラ エラー C3481 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3481
dev_langs: C++
helpviewer_keywords: C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 33bd3d85a4cf44741d59ccb81259babd34704b69
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3481"></a>コンパイラ エラー C3481
'var': ラムダ キャプチャ変数が見つかりません  
  
 コンパイラはラムダ式のキャプチャ リストに渡された変数の定義を見つけられませんでした。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   ラムダ式のキャプチャ リストから変数を削除します。  
  
## <a name="example"></a>例  
 次の例では、変数 `n` が定義されていないため、C3481 が生成されます。  
  
```  
// C3481.cpp  
  
int main()  
{  
   [n] {}(); // C3481  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)