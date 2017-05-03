---
title: "属性 (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# 属性 (C++/CX)
属性は、角かっこ内で [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] の型とメソッドの先頭に付加して、メタデータ作成での特定の動作を指定できるようにする特殊な種類の ref クラスです。 複数の定義済み属性 \([Windows::Foundation::Metadata::WebHostHidden](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.webhosthiddenattribute.aspx) など\) は通常 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] コードで使用されます。 この例では、属性がクラスに適用される方法を示します。  
  
 [!code-cpp[cx_attributes#01](../snippets/cpp/VS_Snippets_Misc/cx_attributes/cpp/class1.h#01)]  
  
## カスタム属性  
 カスタム属性も定義できます。 カスタム属性は、次の [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 規則に従う必要があります。  
  
-   カスタム属性は、パブリック フィールドだけを格納できます。  
  
-   カスタム属性フィールドは、属性がクラスに適用されるときに初期化できます。  
  
-   フィールドは、次に示すいずれかの型になることができます。  
  
    -   int32 \(int\)  
  
    -   uint32 \(unsigned int\)  
  
    -   bool  
  
    -   Platform::String^  
  
    -   Windows::Foundation::HResult  
  
    -   Platform::Type^  
  
    -   パブリック列挙型クラス \(ユーザー定義列挙型を含む\)  
  
 次の例では、カスタム属性を定義し、使用時に初期化する方法を示します。  
  
 [!code-cpp[cx_attributes#02](../snippets/cpp/VS_Snippets_Misc/cx_attributes/cpp/class1.h#02)]  
  
## 参照  
 [型システム \(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)   
 [Visual C\+\+ の言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)