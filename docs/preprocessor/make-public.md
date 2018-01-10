---
title: "make_public |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.make_public
- make_public_CPP
dev_langs: C++
helpviewer_keywords:
- pragmas, make_public
- make_public pragma
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b28c6cd71e8d8ac1165ff6e3afe95ab1f6d4de0f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="makepublic"></a>make_public
ネイティブ型はパブリック アセンブリのアクセシビリティが必要であることを示します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma make_public(type)  
```  
  
### <a name="parameters"></a>パラメーター  
 `type` は、パブリック アセンブリのアクセシビリティを設定する型の名前です。  
  
## <a name="remarks"></a>コメント  
`make_public` は、参照するネイティブ型が、変更できない .h ファイルにある場合に便利です。 パブリック関数のシグニチャでパブリック アセンブリ可視性を持つ型としてネイティブ型を使用する場合は、ネイティブ型にパブリック アセンブリ アクセシビリティもある必要があります。そうでない場合、コンパイラは警告を発行します。  
  
`make_public` はグローバル スコープで指定する必要があり、宣言された時点からソース コード ファイルの末尾まで有効です。  
  
ネイティブな型が暗黙的または明示的に private 可能性があります。参照してください[型の可視性](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)詳細についてはします。  
  
## <a name="example"></a>例  
次のサンプルは、2 つのネイティブ構造体の定義を含む .h ファイルの内容です。  
  
```cpp  
// make_public_pragma.h  
struct Native_Struct_1 { int i; };  
struct Native_Struct_2 { int i; };  
```  
  
## <a name="example"></a>例  
次のコード例は、ヘッダー ファイルを実行し、`make_public` を使用してネイティブの構造がパブリックとして明示的にマークされない限り、ユーザーがパブリック関数とパブリック マネージ型を使用しようとすると、コンパイラが警告を生成することを示します。  
  
```cpp  
// make_public_pragma.cpp  
// compile with: /c /clr /W1  
#pragma warning (default : 4692)  
#include "make_public_pragma.h"  
#pragma make_public(Native_Struct_1)  
  
public ref struct A {  
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK  
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692  
};  
```  
  
## <a name="see-also"></a>参照  
[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)