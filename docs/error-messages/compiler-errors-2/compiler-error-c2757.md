---
title: "コンパイラ エラー C2757 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2757
dev_langs: C++
helpviewer_keywords: C2757
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6100e413c599a9aa6300e6cd7c675c6e2b156178
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2757"></a>コンパイラ エラー C2757
'symbol': この名前のシンボルが既に存在し、そのため、この名前は名前空間の名前として使用できません  
  
 名前空間識別子は参照されたアセンブリで既に使用されているように、現在のコンパイルで使用される記号。  
  
 次の例では、C2757 が生成されます。  
  
```  
// C2757a.cpp  
// compile with: /clr /LD  
public ref class Nes {};  
```  
  
 この場合、次のようになります。  
  
```  
// C2757b.cpp  
// compile with: /clr /c  
#using <C2757a.dll>  
  
namespace Nes {    // C2757  
// try the following line instead  
// namespace Nes2 {  
   public ref class X {};  
}  
```  
