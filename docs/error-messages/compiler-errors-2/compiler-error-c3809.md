---
title: "コンパイラ エラー C3809 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3809
dev_langs:
- C++
helpviewer_keywords:
- C3809
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 22b4406676ced6c2a96241eb15a4329d8933b777
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3809"></a>コンパイラ エラー C3809
'class' : マネージ型または WinRT 型にフレンド関数、クラス、インターフェイスを含めることはできません。  
  
 マネージ型と Windows ランタイム型では、フレンドは許可されません。 このエラーを修復するには、マネージ型または Windows ランタイム型内でフレンドを宣言しないようにします。  
  
 次の例では、C3809 エラーが生成されます。  
  
```  
// C3809a.cpp  
// compile with: /clr  
ref class A {};  
  
ref class B  
{  
public:  
   friend ref class A;   // C3809  
};  
  
int main()  
{  
}  
```