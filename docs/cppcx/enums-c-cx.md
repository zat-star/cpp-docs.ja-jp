---
title: "列挙型 (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
caps.latest.revision: 14
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 14
---
# 列挙型 (C++/CX)
[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] は、標準 C\+\+ `public enum class` に似ている `scoped  enum` キーワードをサポートしています。`public enum class` キーワードを使用して宣言された列挙子を使用する場合、列挙体識別子を使用して各列挙子値の範囲を指定する必要があります。  
  
## コメント  
 `public enum class` など、アクセス指定子を持たない `public` は、標準 C\+\+ の[スコープ列挙体](../Topic/Enumerations%20\(C++\).md)として扱われます。  
  
 `public enum class` または `public enum struct` 宣言の型は、任意の整数型の基となる型 \([!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 自体が int32 型を要求している場合でも\)、またはフラグ列挙用の uint32 にすることができます。 次の構文は、`public enum class` または `public enum struct` の各部分を説明します。 詳細については、「[列挙型クラス](../Topic/enum%20class%20%20\(C++%20Component%20Extensions\).md)」を参照してください。  
  
 この例は、パブリック列挙型クラスを定義する方法を示しています。  
  
 [!code-cpp[cx_enums#01](../snippets/cpp/VS_Snippets_Misc/cx_enums/cpp/class1.h#01)]  
  
 この次の例では、それを利用する方法を示しています。  
  
 [!code-cpp[cx_enums#02](../snippets/cpp/VS_Snippets_Misc/cx_enums/cpp/class1.h#02)]  
  
## 例  
 次の例は、列挙型を宣言する方法を示します。  
  
 [!code-cpp[cx_enums#03](../snippets/cpp/VS_Snippets_Misc/cx_enums/cpp/class1.h#03)]  
  
 次の例は、同等の数値にキャストし、比較を実行する方法を示しています。 列挙子 `One` の使用範囲は `Enum1` 列挙体識別子により指定され、列挙子 `First` の範囲は `Enum2` によって指定されることに注意してください。  
  
 [!code-cpp[cx_enums#04](../snippets/cpp/VS_Snippets_Misc/cx_enums/cpp/class1.h#04)]  
  
## 参照  
 [型システム](../cppcx/type-system-c-cx.md)   
 [Visual C\+\+ の言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)