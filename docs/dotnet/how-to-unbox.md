---
title: "方法: ボックス化解除 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- unboxing
ms.assetid: 75794696-9275-47bf-9a7d-5abe6585ab91
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 94e9403d7def0603fc8be56ce1bd0d67db8911b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-unbox"></a>方法: ボックス化を解除する
ボックス化を解除し、値を変更する方法を示します。  
  
## <a name="example"></a>例  
  
```  
// vcmcppv2_unboxing.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   int ^ i = gcnew int(13);  
   int j;  
   Console::WriteLine(*i);   // unboxing  
   *i = 14;   // unboxing and assignment  
   Console::WriteLine(*i);  
   j = safe_cast<int>(i);   // unboxing and assignment  
   Console::WriteLine(j);  
}  
```  
  
```Output  
13  
14  
14  
```  
  
## <a name="see-also"></a>参照  
 [ボックス化](../windows/boxing-cpp-component-extensions.md)