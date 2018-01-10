---
title: "ボックス化 (C + + CX) |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
caps.latest.revision: "12"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5d953e35c0fe238dc8dee76ad6c2d5aab7a0ab1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="boxing-ccx"></a>ボックス化 (C++/CX)
*ボックス化* とは、入力型として [Platform::Object^](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx)を取るメソッドに変数が渡されたときに、ref クラス内で、値の型変数 ( `int`Windows::Foundation::DateTime [など) または基本的スカラー型 (](../cppcx/platform-object-class.md) など) をラップすることです。  
  
## <a name="passing-a-value-type-to-an-object-parameter"></a>Object^ パラメーターへの値の型の引き渡し  
 変数を明示的にボックス化しなくても、型 [Platform::Object^](../cppcx/platform-object-class.md)のメソッド パラメーターに渡すことはできますが、以前にボックス化されたことがある値を取得するときは、明示的にキャストして元の型に戻す必要があります。  
  
 [!code-cpp[cx_boxing#01](../cppcx/codesnippet/CPP/cx_boxing/class1.cpp#01)]  
  
### <a name="using-platformiboxt-to-support-nullable-value-types"></a>Platform::ibox 使用\<T > を null 許容値型をサポートするには  
 C# および Visual Basic では、null 許容値型の概念をサポートしています。 C + + CX、行うこともできます、 `Platform::IBox<T>` null 許容値型パラメーターをサポートするパブリック メソッドを公開する型。 次の例は、C + + CX のパブリック メソッド、c# 呼び出し元が null の引数を渡すと null を返すにします。  
  
 [!code-cpp[cx_boxing#02](../cppcx/codesnippet/CPP/cx_boxing/class1.h#02)]  
  
 C# XAML クライアントでは、これを次のように利用できます。  
  
```  
  
// C# client code  
    BoxingDemo.Class1 obj = new BoxingDemo.Class1();  
    int? a = null;  
    int? b = 5;  
    var result = obj.Multiply(a,b); //result = null  
  
```  
  
## <a name="see-also"></a>参照  
 [型システム (C++/CX)](../cppcx/type-system-c-cx.md)   
 [キャスト (C + + CX)](../cppcx/casting-c-cx.md)   
 [Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)