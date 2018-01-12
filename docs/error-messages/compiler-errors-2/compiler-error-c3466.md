---
title: "コンパイラ エラー C3466 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3466
dev_langs: C++
helpviewer_keywords: C3466
ms.assetid: 69a877d9-a749-474b-bfc3-8d3fd53ba8fd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: af992f70d3e2a673c098d3e412e6368dc2f64b02
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3466"></a>コンパイラ エラー C3466
'type': ジェネリック クラスの特殊化を転送することはできません  
  
 型のジェネリック クラスの特殊化の転送を使用することはできません。  
  
 詳細については、次を参照してください。 [Type Forwarding (C + + CLI)](../../windows/type-forwarding-cpp-cli.md)です。  
  
## <a name="example"></a>例  
 コンポーネントを作成する例を次に示します。  
  
```  
// C3466.cpp  
// compile with: /clr /LD  
generic<typename T>  
public ref class GR {};  
  
public ref class GR2 {};  
```  
  
## <a name="example"></a>例  
 次の例では C3466 が生成されます。  
  
```  
// C3466_b.cpp  
// compile with: /clr /c  
#using "C3466.dll"  
[assembly:TypeForwardedTo(GR<int>::typeid)];   // C3466  
[assembly:TypeForwardedTo(GR2::typeid)];   // OK  
```