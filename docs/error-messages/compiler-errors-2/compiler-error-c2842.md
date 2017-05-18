---
title: "コンパイラ エラー C2842 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2842
dev_langs:
- C++
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: e4b3067b3293892d25dace565538a022e49a6f6f
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2842"></a>コンパイラ エラー C2842
'class' : マネージ型または WinRT 型はそれ自体の 'operator new' または 'operator delete' を定義できません  
  
 独自に定義することができます**new 演算子または**演算子 delete * * をネイティブ ヒープにメモリの割り当てを管理します。 ただし、これらの演算子はマネージ ヒープでのみ割り当てられるため、参照クラスでは定義できません。  

  
 詳細については、次を参照してください。[ユーザー定義演算子 (C + +/CLI)](../../dotnet/user-defined-operators-cpp-cli.md)します。  
  
## <a name="example"></a>例  
 次の例では C2842 が生成されます。  
  
```  
// C2842.cpp  
// compile with: /clr /c  
ref class G {  
   void* operator new( size_t nSize );   // C2842  
};  
```  

