---
title: "コンパイラ COM サポート クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 48540910db97e7662eeaa7e8a7febf7e44df653b
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="compiler-com-support-classes"></a>コンパイラ COM サポート クラス
**Microsoft 固有の仕様**  
  
 標準クラスは、COM 型の一部をサポートするために使用されます。 クラスは、comdef.h ファイル、およびタイプ ライブラリから生成されたヘッダー ファイルで定義されます。  
  
|クラス|目的|  
|-----------|-------------|  
|[_bstr_t](../cpp/bstr-t-class.md)|便利な演算子とメソッドを提供するために、`BSTR` 型をラップします。|  
|[_com_error](../cpp/com-error-class.md)|によってスローされたエラー オブジェクトを定義[_com_raise_error](../cpp/com-raise-error.md)でほとんどの障害が発生します。|  
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|COM インターフェイス ポインターをカプセル化し、必要な呼び出しを自動化`AddRef`、**リリース**、および`QueryInterface`です。|  
|[_variant_t](../cpp/variant-t-class.md)|ラップ、**バリアント**便利な演算子とメソッドを提供する型。|  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ COM サポート](../cpp/compiler-com-support.md)   
 [コンパイラ COM グローバル関数](../cpp/compiler-com-global-functions.md)   
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)
