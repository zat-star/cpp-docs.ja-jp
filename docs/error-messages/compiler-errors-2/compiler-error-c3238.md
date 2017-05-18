---
title: "コンパイラ エラー C3238 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3238
dev_langs:
- C++
helpviewer_keywords:
- C3238
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
caps.latest.revision: 9
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 7f9ddf5c7772bfed7c1789e9927cbe46bd1f712c
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3238"></a>コンパイラ エラー C3238
'type' : この名前の型は、アセンブリ 'assembly' に既に転送されました  
  
 クライアント アプリケーションで定義された型は、参照されているアセンブリでも、型の転送構文によって定義されています。 アプリケーションのスコープで、両方の型を定義することはできません。  
  
 参照してください[Type Forwarding (C + + CLI)](../../windows/type-forwarding-cpp-cli.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では、別のアセンブリから転送された型を含むアセンブリを作成します。  
  
```  
// C3238.cpp  
// compile with: /clr /LD  
public ref class R {};  
```  
  
## <a name="example"></a>例  
 次の例は型定義を含んでいたアセンブリを作成しますが、型の転送構文だけを含んでいるわけではありません。  
  
```  
// C3238_b.cpp  
// compile with: /clr /LD  
#using "C3238.dll"  
[ assembly:TypeForwardedTo(R::typeid) ];  
```  
  
## <a name="example"></a>例  
 次の例では C3238 が生成されます。  
  
```  
// C3238_c.cpp  
// compile with: /clr /c  
// C3238 expected  
// Delete the following line to resolve.  
#using "C3238_b.dll"  
public ref class R {};  
```
