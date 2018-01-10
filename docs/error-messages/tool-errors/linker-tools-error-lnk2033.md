---
title: "リンカ ツール エラー LNK2033 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2033
dev_langs: C++
helpviewer_keywords: LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bac0d88d8e1ba06c358a6a1dd410b861dc582cdc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2033"></a>リンカ ツール エラー LNK2033
'type' の未解決の typeref トークン (トークン)  
  
 MSIL のメタデータに型の定義がありません。  
  
 LNK2033 はでコンパイルするときに発生する可能性が**/clr:safe**が MSIL モジュールの MSIL モジュールの種類が参照されている場所にある種類の事前宣言のみが存在するとします。  
  
 型の下で定義する必要があります**/clr:safe**です。  
  
 詳細については、「[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、LNK2033 が生成されます。  
  
```  
// LNK2033.cpp  
// compile with: /clr:safe  
// LNK2033 expected  
ref class A;  
ref class B {};  
  
int main() {  
   A ^ aa = nullptr;  
   B ^ bb = nullptr;   // OK  
};  
```