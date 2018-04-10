---
title: コンパイラ エラー C3755 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C3755
dev_langs:
- C++
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b1b3db9fdc6b408476c4d5213cea3c3e58b6f14
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3755"></a>コンパイラ エラー C3755
'delegate': デリゲートを定義することがない可能性があります  
  
 A [delegate (C++ コンポーネント拡張)](../../windows/delegate-cpp-component-extensions.md)宣言しますが、定義されていないことができます。  
  
## <a name="example"></a>例  
 次の例では、C3755 を生成します。  
  
```  
// C3755.cpp  
// compile with: /clr /c  
delegate void MyDel() {};   // C3755  
```  
  
## <a name="example"></a>例  
 C3755 は、デリゲートのテンプレートを作成しようとする場合にも発生することができます。 次の例では、C3755 を生成します。  
  
```  
// C3755_b.cpp  
// compile with: /clr /c  
ref struct R {  
   template<class T>  
   delegate void D(int) {}   // C3755  
};  
```