---
title: "コンパイラ エラー C2599 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2599
dev_langs:
- C++
helpviewer_keywords:
- C2599
ms.assetid: 88515f36-7589-47e2-862e-0de8b18d6668
caps.latest.revision: 17
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
ms.openlocfilehash: 68971aec52fb03532b74be3b231598abfc0e8f6f
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2599"></a>コンパイラ エラー C2599
'enum': 列挙型の事前宣言が許可されていません  
  
 コンパイラは、管理されている列挙の事前宣言をサポートしていません。  
  
 列挙型の事前宣言が許可されていません[/Za](../../build/reference/za-ze-disable-language-extensions.md)します。  
  
 次の例は、c2599 エラーを生成します。  
  
```  
// C2599.cpp  
// compile with: /clr /c  
enum class Status;   // C2599  
  
enum class Status2 { stop2, hold2, go2};   
  
ref struct MyStruct {  
   // Delete the following line to resolve.  
   Status m_status;  
  
   Status2 m_status2;   // OK  
};  
  
enum class Status { stop, hold, go };  
```
