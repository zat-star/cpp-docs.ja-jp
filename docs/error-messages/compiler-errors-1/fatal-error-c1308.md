---
title: "致命的なエラー C1308 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1308
dev_langs:
- C++
helpviewer_keywords:
- C1308
ms.assetid: 46177997-069e-433a-8e20-93c846d78ffd
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f9958ccb3daa537f8789d7485822fd623da8c703
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

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
