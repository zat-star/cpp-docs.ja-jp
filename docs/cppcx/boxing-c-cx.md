---
title: "ボックス化 (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
caps.latest.revision: 12
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 12
---
# ボックス化 (C++/CX)
*ボックス化*とは、入力型として [Platform::Object^](../cppcx/platform-object-class.md) を取るメソッドに変数が渡されたときに、ref クラス内で、値の型変数 \([Windows::Foundation::DateTime](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx) など\) または基本的スカラー型 \(`int` など\) をラップすることです。  
  
## Object^ パラメーターへの値の型の引き渡し  
 変数を明示的にボックス化しなくても、型 [Platform::Object^](../cppcx/platform-object-class.md) のメソッド パラメーターに渡すことはできますが、以前にボックス化されたことがある値を取得するときは、明示的にキャストして元の型に戻す必要があります。  
  
 [!code-cpp[cx_boxing#01](../snippets/cpp/VS_Snippets_Misc/cx_boxing/cpp/class1.cpp#01)]  
  
### Platform::IBox\<T\> の使用による null 許容値型のサポート  
 C\# および Visual Basic では、null 許容値型の概念をサポートしています。[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] では、`Platform::IBox<T>` 型を使用して、null 許容値型パラメーターをサポートするパブリック メソッドを公開できます。 次の例では、C\# 呼び出し元が引数の 1 つに null を渡すと null を返す [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] パブリック メソッドを示しています。  
  
 [!code-cpp[cx_boxing#02](../snippets/cpp/VS_Snippets_Misc/cx_boxing/cpp/class1.h#02)]  
  
 C\# XAML クライアントでは、これを次のように利用できます。  
  
```  
  
// C# client code BoxingDemo.Class1 obj = new BoxingDemo.Class1(); int? a = null; int? b = 5; var result = obj.Multiply(a,b); //result = null  
  
```  
  
## 参照  
 [型システム \(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)   
 [キャスト \(C\+\+\/CX\)](../cppcx/casting-c-cx.md)   
 [Visual C\+\+ の言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)