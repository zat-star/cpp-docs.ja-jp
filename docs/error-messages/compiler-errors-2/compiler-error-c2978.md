---
title: "コンパイラ エラー C2978 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2978
dev_langs:
- C++
helpviewer_keywords:
- C2978
ms.assetid: 5e7bee82-e266-4ccd-ad2e-ee89606ec5bf
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3d02f0844cf3abe975531ec0560441c8eedd1ba6
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2978"></a>コンパイラ エラー C2978
構文エラー: 'keyword1' または 'keyword2' が必要ですが、型 'keyword3' が見つかりました。非型パラメーターはジェネリックではサポートされていません  
  
 ジェネリック クラスの宣言が正しくありません。 参照してください[ジェネリック](../../windows/generics-cpp-component-extensions.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では C2978 が生成されます。  
  
```  
// C2978.cpp  
// compile with: /clr /c  
generic <ref class T>   // C2978  
// try the following line instead  
// generic <typename T>   // OK  
ref class Utils {  
   static void sort(T elems, size_t size);  
};  
  
generic <int>  
// try the following line instead  
// generic <class T>  
ref class Utils2 {  
   static void sort(T elems, size_t size);  
};  
```
