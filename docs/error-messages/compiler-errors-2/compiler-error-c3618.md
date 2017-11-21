---
title: "コンパイラ エラー C3618 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3618
dev_langs: C++
helpviewer_keywords: C3618
ms.assetid: cacc105d-4389-4cb8-ae6c-41a3622e9a86
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3b014cb60c2e9a65888fa425f4046c118cfc31d2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3618"></a>コンパイラ エラー C3618
'function': DllImport マークされたメソッドを定義することはできません  
  
 マークされたメソッド<xref:System.Runtime.InteropServices.DllImportAttribute>が定義されている、指定しました。DLL です。  
  
## <a name="example"></a>例  
 次の例では、c3618 エラーを生成します。  
  
```  
// C3618.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[ DllImport("user32.dll", EntryPoint="MessageBox", CharSet=CharSet::Ansi) ]  // CHANGED   
void Func();   
  
void Func() {}   // C3618, remove this function definition to resolve  
```