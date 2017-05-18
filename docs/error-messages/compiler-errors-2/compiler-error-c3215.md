---
title: "コンパイラ エラー C3215 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3215
dev_langs:
- C++
helpviewer_keywords:
- C3215
ms.assetid: d0d16007-8885-42e0-b086-2d3a61f348c5
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
ms.openlocfilehash: 331de627b05a57d630b83bd20a625e368527631e
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3215"></a>コンパイラ エラー C3215
'type1': 'type2' によって既に制限されているジェネリック型パラメーターです  
  
 制約が複数回指定されました。  
  
 ジェネリックの詳細については、次を参照してください。[ジェネリック](../../windows/generics-cpp-component-extensions.md)です。  
  
 次の例では C3215 が生成されます。  
  
```  
// C3215.cpp  
// compile with: /clr  
interface struct A {};  
  
generic <class T>  
where T : A,A  
ref class C {};   // C3215  
```  
  
 考えられる解決策:  
  
```  
// C3215b.cpp  
// compile with: /clr /c  
interface struct A {};  
  
generic <class T>  
where T : A  
ref class C {};  
```
