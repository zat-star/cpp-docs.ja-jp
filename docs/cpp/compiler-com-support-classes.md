---
title: "コンパイラ COM サポート クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_raise_error
dev_langs: C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 54377893135c2b933c25387bccbb750d2f3eb734
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2018
---
# <a name="compiler-com-support-classes"></a>コンパイラ COM サポート クラス
**Microsoft 固有の仕様**  
  
 標準クラスは、COM 型の一部をサポートするために使用されます。 クラスが定義されている\<comdef.h > と、タイプ ライブラリから生成されたヘッダー ファイルです。  
  
|クラス|目的|  
|-----------|-------------|  
|[_bstr_t](../cpp/bstr-t-class.md)|便利な演算子とメソッドを提供するために、`BSTR` 型をラップします。|  
|[_com_error](../cpp/com-error-class.md)|によってスローされたエラー オブジェクトを定義[_com_raise_error](../cpp/com-raise-error.md)でほとんどの障害が発生します。|  
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|COM インターフェイス ポインターをカプセル化し、必要な呼び出しを自動化`AddRef`、**リリース**、および`QueryInterface`です。|  
|[_variant_t](../cpp/variant-t-class.md)|ラップ、**バリアント**便利な演算子とメソッドを提供する型。|  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [コンパイラ COM サポート](../cpp/compiler-com-support.md)   
 [コンパイラ COM グローバル関数](../cpp/compiler-com-global-functions.md)   
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)