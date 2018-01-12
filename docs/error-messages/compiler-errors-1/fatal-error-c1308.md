---
title: "致命的なエラー C1308 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1308
dev_langs: C++
helpviewer_keywords: C1308
ms.assetid: 46177997-069e-433a-8e20-93c846d78ffd
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4be04f3891e39c37924743ae86e2c7f62f92b6d8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1308"></a>致命的なエラー C1308
リンク アセンブリはサポートされていません  
  
 .Netmodule が、リンカーへの入力として可能ですが、アセンブリがありません。 コンパイルされたアセンブリにリンクする試みが行われたときに、このエラーを生成できる`/clr:safe`です。  
  
 詳細については、「 [リンカー入力としての .netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md)」を参照してください。  
  
 次の例では、C1308 が生成されます。  
  
```  
// C1308.cpp  
// compile with: /clr:safe /LD  
public ref class MyClass {  
public:  
   int i;  
};  
```  
  
 それから  
  
```  
// C1308b.cpp  
// compile with: /clr /link C1308b.obj C1308.dll  
// C1308 expected  
#using "C1308.dll"  
int main() {  
   MyClass ^ my = gcnew MyClass();  
}  
```