---
title: "コンパイラ エラー C3908 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3908
dev_langs:
- C++
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3c364709704e5051bcfcb77777d15b18d46b375
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3908"></a>コンパイラ エラー C3908
'construct' より少ない制限の厳しいアクセス レベル  
  
 プロパティ アクセサー メソッド (get または set) は、プロパティ自体に指定されたアクセスよりも制限の緩いアクセスにはできません。  同様に、イベントのアクセサー メソッドの  
  
 詳細については、次を参照してください。[プロパティ](../../windows/property-cpp-component-extensions.md)と[イベント](../../windows/event-cpp-component-extensions.md)です。  
  
 次の例では、C3908 が生成されます。  
  
```  
// C3908.cpp  
// compile with: /clr  
ref class X {  
protected:  
   property int i {  
   public:   // C3908 property i is protected   
      int get();  
   private:  
      void set(int);   // OK more restrictive  
   };  
};  
```