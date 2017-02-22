---
title: "functional (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "<cliext/functional>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/functional> ヘッダー [STL/CLR]"
  - "<functional> ヘッダー [STL/CLR]"
  - "機能性関数 [STL/CLR]"
ms.assetid: 88738b8c-5d37-4375-970e-a4442bf5efde
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# functional (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

多数のテンプレート クラスおよび関連テンプレートのデリゲートと関数定義に STL\/CLR のヘッダー `<cliext/functional>` を含めます。  
  
## 構文  
  
```  
#include <functional>  
```  
  
## 宣言  
  
|Delegate|説明|  
|--------------|--------|  
|[binary\_delegate](../Topic/binary_delegate%20\(STL-CLR\).md)|2 引数をデリゲート。|  
|[binary\_delegate\_noreturn](../dotnet/binary-delegate-noreturn-stl-clr.md)|`void`を返します。2 引数をデリゲート。|  
|[unary\_delegate](../dotnet/unary-delegate-stl-clr.md)|1 引数をデリゲート。|  
|[unary\_delegate\_noreturn](../dotnet/unary-delegate-noreturn-stl-clr.md)|`void`を返します。1 引数をデリゲート。|  
  
|\[クラス\]|説明|  
|-------------|--------|  
|[binary\_negate](../dotnet/binary-negate-stl-clr.md)|2 引数のファンクタを拒否するファンクタ。|  
|[binder1st](../dotnet/binder1st-stl-clr.md)|2 引数のファンクタに最初の引数をバインドするファンクタ。|  
|[binder2nd](../Topic/binder2nd%20\(STL-CLR\).md)|2 引数のファンクタの 2 番目の引数をバインドするファンクタ。|  
|[divides](../dotnet/divides-stl-clr.md)|除算のファンクタ。|  
|[equal\_to](../dotnet/equal-to-stl-clr.md)|等価比較のファンクタ。|  
|[greater](../dotnet/greater-stl-clr.md)|大規模な比較のファンクタ。|  
|[greater\_equal](../Topic/greater_equal%20\(STL-CLR\).md)|拡大または等価比較のファンクタ。|  
|[less](../dotnet/less-stl-clr.md)|よりも比較のファンクタ。|  
|[less\_equal](../dotnet/less-equal-stl-clr.md)|より小さいまたは等価比較のファンクタ。|  
|[logical\_and](../dotnet/logical-and-stl-clr.md)|論理演算子、ファンクタ。|  
|[logical\_not](../dotnet/logical-not-stl-clr.md)|論理 NOT ファンクタ。|  
|[logical\_or](../Topic/logical_or%20\(STL-CLR\).md)|論理 OR ファンクタ。|  
|[minus](../dotnet/minus-stl-clr.md)|ファンクタを描画します。|  
|[剰余](../dotnet/modulus-stl-clr.md)|残りのファンクタ。|  
|[multiplies](../Topic/multiplies%20\(STL-CLR\).md)|ファンクタを大きくします。|  
|[negate](../Topic/negate%20\(STL-CLR\).md)|拒否された引数を返すファンクタ。|  
|[not\_equal\_to](../dotnet/not-equal-to-stl-clr.md)|等価比較のファンクタ。|  
|[plus](../dotnet/plus-stl-clr.md)|ファンクタを追加します。|  
|[unary\_negate](../dotnet/unary-negate-stl-clr.md)|1 引数のファンクタを拒否するファンクタ。|  
  
|関数|説明|  
|--------|--------|  
|[bind1st](../dotnet/bind1st-stl-clr.md)|引数とファンクタの binder1st を生成します。|  
|[bind2nd](../dotnet/bind2nd-stl-clr.md)|引数とファンクタの binder2nd を生成します。|  
|[not1](../dotnet/not1-stl-clr.md)|ファンクタの unary\_negate を生成します。|  
|[not1](../dotnet/not1-stl-clr.md)|ファンクタの binary\_negate を生成します。|  
  
## 必要条件  
 **ヘッダー:** の \<cliext と機能\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [STL\/CLR ライブラリ](../dotnet/stl-clr-library-reference.md)