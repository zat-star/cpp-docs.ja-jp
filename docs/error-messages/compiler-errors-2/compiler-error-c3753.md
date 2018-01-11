---
title: "コンパイラ エラー C3753 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3753
dev_langs: C++
helpviewer_keywords: C3753
ms.assetid: a5b99e28-796c-4107-a673-97c2ae3bb2b9
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f68e4fb49116418377235a283eadbf2f28e92885
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3753"></a>コンパイラ エラー C3753
ジェネリック プロパティは使用できません。  
  
 ジェネリック パラメーター リストは、マネージ クラス、構造体、または関数でのみ使用できます。  
  
 詳細については、次を参照してください。[ジェネリック](../../windows/generics-cpp-component-extensions.md)と[プロパティ](../../windows/property-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3753 を生成します。  
  
```  
// C3753.cpp  
// compile with: /clr /c  
ref struct A {  
   generic <typename T>  
   property int i;   // C3753 error  
};  
```