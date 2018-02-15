---
title: "列挙型 (C + + CX) |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b3a95af557dd416d99368dbd1ab51495e0bd1d85
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="enums-ccx"></a>列挙型 (C++/CX)
C + + CX をサポートしている、`public enum class`キーワードは、標準の C++ に似ている`scoped  enum`です。 `public enum class` キーワードを使用して宣言された列挙子を使用する場合、列挙体識別子を使用して各列挙子値の範囲を指定する必要があります。  
  
### <a name="remarks"></a>コメント  
 `public enum class` など、アクセス指定子を持たない `public`は、標準 C++ の [スコープ列挙体](../cpp/enumerations-cpp.md)として扱われます。  
  
 A`public enum class`または`public enum struct`Windows ランタイム自体は、型が int32、またはフラグ列挙用の uint32 にすることが必要ですが、宣言は任意の整数型の基になる型を持つことができます。 次の構文は、 `public enum class` または `public enum struct`の各部分を説明します。  
  
 この例は、パブリック列挙型クラスを定義する方法を示しています。  
  
 [!code-cpp[cx_enums#01](../cppcx/codesnippet/CPP/cpp/class1.h#01)]  
  
 この次の例では、それを利用する方法を示しています。  
  
 [!code-cpp[cx_enums#02](../cppcx/codesnippet/CPP/cpp/class1.h#02)]  
  
### <a name="examples"></a>使用例  
 次の例は、列挙型を宣言する方法を示します。  
  
 [!code-cpp[cx_enums#03](../cppcx/codesnippet/CPP/cpp/class1.h#03)]  
  
 次の例は、同等の数値にキャストし、比較を実行する方法を示しています。 列挙子 `One` の使用範囲は `Enum1` 列挙体識別子により指定され、列挙子 `First` の範囲は `Enum2`によって指定されることに注意してください。  
  
 [!code-cpp[cx_enums#04](../cppcx/codesnippet/CPP/cpp/class1.h#04)]  
  
## <a name="see-also"></a>参照  
 [型システム](../cppcx/type-system-c-cx.md)   
 [Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)