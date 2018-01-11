---
title: "alloc_text |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.alloc_text
- alloc_text_CPP
dev_langs: C++
helpviewer_keywords:
- alloc_text pragma
- pragmas, alloc_text
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b54008652c036530135ca6d180398cb328fdb2da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="alloctext"></a>alloc_text
指定した関数定義が存在するコード セクションに名前を付けます。 このプラグマは、名前付き関数の関数宣言子と関数定義との間で指定する必要があります。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma alloc_text( "  
textsection  
", function1, ... )  
```  
  
## <a name="remarks"></a>コメント  
 **Alloc_text**プラグマでは、C++ メンバー関数またはオーバー ロードされた関数は処理しません。 これは C リンケージで宣言された関数にのみ適用: で宣言された関数、 **extern"C"**リンケージ指定します。 C++ リンケージを持つ関数でこのプラグマを使用しようとすると、コンパイラ エラーが生成されます。  
  
 アドレス指定を使用して関数から`__based`はサポートされていません、セクションの場所の使用を要求を指定する、 **alloc_text**プラグマ。 指定した名前*textsection*二重引用符で囲む必要があります。  
  
 **Alloc_text**プラグマが、これらの関数の定義の前に指定された関数のいずれかの宣言の後に置く必要があります。  
  
 参照される関数、 **alloc_text**プラグマは、プラグマと同じモジュールで定義する必要があります。 これが実行されず、未定義の関数が別のテキスト セクションに後でコンパイルされると、エラーがキャッチされる場合とキャッチされない場合があります。 プログラムは正常に動作しますが、関数は目的のセクションでは割り当てられません。  
  
 に関するその他の制限事項**alloc_text**次に示します。  
  
-   関数内では使用できません。  
  
-   関数が宣言された後で、関数が定義される前に使用する必要があります。  
  
## <a name="see-also"></a>参照  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)