---
title: "コンパイラの警告 C4687 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4687
dev_langs:
- C++
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
caps.latest.revision: 5
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: f2dc847b6d75a563379b46e1375f93ceab9c7531
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4687"></a>コンパイラの警告 C4687
'class': シールされた抽象クラスはインターフェイス 'インターフェイス' を実装することはできません  
  
 シールされた抽象型は通常静的メンバー関数を保持すると便利です。  
  
 詳細については、次を参照してください。[抽象](../../windows/abstract-cpp-component-extensions.md)と[シール](../../windows/sealed-cpp-component-extensions.md)します。  
  
 C4687 は既定では、エラーとして発行します。 C4687 を抑制することができます、[警告](../../preprocessor/warning.md)プラグマです。 シールされた抽象型にインターフェイスを実装する場合は、C4687 を抑制することができます。  
  
## <a name="example"></a>例  
 次の例では、C4687 を生成します。  
  
```  
// C4687.cpp  
// compile with: /clr /c  
interface class A {};  
  
ref struct B sealed abstract : A {};   // C4687  
ref struct C sealed : A {};   // OK  
ref struct D abstract : A {};   // OK  
```
