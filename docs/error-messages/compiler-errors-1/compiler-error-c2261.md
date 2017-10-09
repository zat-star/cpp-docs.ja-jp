---
title: "コンパイラ エラー C2261 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2261
dev_langs:
- C++
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8269b891ed899501625973b81c1823d4db2d56c8
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2261"></a>コンパイラ エラー C2261
'string': アセンブリ参照が有効ではありません、解決できません。  
  
 値が無効でした。  
  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>フレンド アセンブリの指定に使用されます。 たとえば、a.dll は、フレンド アセンブリとして b.dll を指定する必要がある場合とで指定した (a.dll): InternalsVisibleTo("b") です。 ランタイムには、b.dll a.dll (プライベート型) を除くのすべてのアクセスが許可されます。  
  
 フレンド アセンブリを指定する場合は、正しい構文の詳細は、次を参照してください。[フレンド アセンブリ (C++)](../../dotnet/friend-assemblies-cpp.md)です。  
  
## <a name="example"></a>例  
 次の例では、C2261 を生成します。  
  
```  
// C2261.cpp  
// compile with: /clr /c  
using namespace System::Runtime::CompilerServices;  
[assembly: InternalsVisibleTo("a,a,a")];   // C2261  
[assembly: InternalsVisibleTo("a.a")];   // OK  
[assembly: InternalsVisibleTo("a")];   // OK  
```
