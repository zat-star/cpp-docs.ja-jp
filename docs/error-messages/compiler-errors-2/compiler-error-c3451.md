---
title: "コンパイラ エラー C3451 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3451
dev_langs: C++
helpviewer_keywords: C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cb68c546a9064801c68844039b7de077d5ee7c17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3451"></a>コンパイラ エラー C3451
'attribute': アンマネージ属性を 'type' を適用することはできません  
  
 C++ 属性は、CLR 型に適用できません。 参照してください[C++ 属性リファレンス](../../windows/cpp-attributes-reference.md)詳細についてはします。  
  
 詳細については、「 [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)」を参照してください。  
  
 このエラーは、Visual C 2005 で行ったコンパイラ準拠作業の結果として生成されることができます。 [uuid](../../windows/uuid-cpp-attributes.md) CLR プログラミングを使用して、ユーザー定義属性の属性が許可されていません。 代わりに、<xref:System.Runtime.InteropServices.GuidAttribute> を使用してください。  
  
## <a name="example"></a>例  
 次の例では、C3451 を生成します。  
  
```  
// C3451.cpp  
// compile with: /clr /c  
using namespace System;  
[ attribute(AttributeTargets::All) ]  
public ref struct MyAttr {};  
  
[ MyAttr, helpstring("test") ]   // C3451  
// try the following line instead  
// [ MyAttr ]  
public ref struct ABC {};  
```